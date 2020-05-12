<!-- template to remove different types of html tags -->
<xsl:template name="remove_html">
    <xsl:param name="text" />
    <xsl:choose>
        <!-- remove DOCTYPE -->
        <xsl:when test="contains($text, '&lt;!DOCTYPE')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, '&lt;!DOCTYPE.*?&gt;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove <html> and <html> und </html> -->
        <xsl:when test="contains($text, '&lt;html')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace(replace($text, '&lt;html.*?&gt;', ''), '&lt;/html.*?&gt;','')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove the total header. -->
        <xsl:when test="contains($text, '&lt;head&gt;')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, '&lt;head&gt;.*?&lt;/head&gt;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove <body> and </body> -->
        <xsl:when test="contains($text, '&lt;body')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace(replace($text, '&lt;body.*?&gt;', ''), '&lt;/body.*?&gt;','')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove <script> and the content between <script> and </script> -->
        <xsl:when test="contains($text, '&lt;script&gt;')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, '&lt;script&gt;.*?&lt;/script&gt;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove <div> and </div> -->
        <xsl:when test="contains($text, '&lt;div')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace(replace($text, '&lt;div.*?&gt;', ''), '&lt;/div.*?&gt;','')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove comments -->
        <xsl:when test="contains($text, '&lt;!--')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, '&lt;!--.*?--&gt;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove links using <a> -->
        <xsl:when test="contains($text, '&lt;a')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace(replace($text, '&lt;a.*?&gt;', ''), '&lt;/a.*?&gt;','')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove images -->
        <xsl:when test="contains($text, '&lt;img')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, '&lt;img.*?&gt;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove calsses -->
        <xsl:when test="contains($text, 'class=&quot;')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, 'class=&quot;.*?&quot;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove links using href -->
        <xsl:when test="contains($text, 'href=&quot;')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, 'href=&quot;.*?&quot;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- remove css using style= -->
        <xsl:when test="contains($text, 'style=&quot;')">
            <xsl:call-template name="remove_html">
                <xsl:with-param name="text" select="replace($text, 'style=&quot;.*?&quot;', '')" />
            </xsl:call-template>
        </xsl:when>
        <!-- if the content is clear, give out the value -->
        <xsl:otherwise>
            <xsl:value-of select="normalize-space($text)" />
        </xsl:otherwise>
    </xsl:choose>
</xsl:template>
 
 
<!-- call template to clean up xml value e.g. <content> -->
<content>
    <xsl:call-template name="remove_html">
        <xsl:with-param name="text" select="normalize-space(content)" />
    </xsl:call-template>
</content>
