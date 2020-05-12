<xsl:variable name="String">
    <xsl:value-of select="normalize-space(keywords)" />
</xsl:variable>
<xsl:variable name="tokenizedString" select="tokenize($String,',')" />
<xsl:for-each select="$tokenizedString">
    <key>
        <xsl:value-of select="normalize-space(.)" />
    </key>
</xsl:for-each>
