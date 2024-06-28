# XSS in WordPress Theme - MDx (<= 2.0.3)
## Description
The shortcode implementation in the MDx WordPress theme lacks essential input validation and character escaping measures. Consequently, users with contributor-level privileges can exploit this vulnerability by creating new posts containing malicious shortcode payloads. Such payloads have the potential to trigger harmful Cross-Site Scripting (XSS) attacks that could compromise the security of the administrator.
## Proof of Concept
With contributer+ privilege. Create a post and embed the following: 
```
[mdx_list_item action='test" onmouseover="alert(/XSS/)']test[/mdx_list_item]
```

## Reference
https://github.com/yrccondor/mdx
