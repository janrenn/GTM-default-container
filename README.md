# GTM default container

1. Replace all variable placeholders limited with `%%`
2. Import to https://tagmanager.google.com/?hl=en#/admin/ container

## Variables

```
%%ACCOUNT_ID%%
%%CONTAINER_ID%%
%%CONTAINER_NAME%%
%%CONTAINER_PUBLIC_ID%%
%%HOST_NAME%%
```

## Implementation Checklist

1. Create GA account (or choose an existing)
2. Create GA property www.example.com, basic setup -- industry, timezone
3. Save tracking ID, ex. `UA-12345678-9`
4. Rename default view: *All Web Site Data* -> ***Backup RAW profile***, setup currency + search
5. Copy views to ***Optimized PROD profile*** and ***TEST profile***
6. *Property Settings* -> default view to **Optimized**
7. *Property Settings* -> Enable **Demographics and Interest Reports** + **Use enhanced link attribution** -> Save
8. Insert GTM code on every page of production site (via admin, template or another method), eventually add  
`<script>var dataLayer = dataLayer || [];</script>` before the first code part
9. Setup ***Search Console*** (https://www.google.com/webmasters/tools)
10. Connect *Search Console* with *GA*
11. *GA -> property -> tracking info -> data collection ->* **Remarketing ON**
12. *Optimized PROD profile ->* **Exclude all hits from known bots and spiders**
13. *Optimized PROD profile -> Goals ->* import basic sets from library (search for *janrenn*)
14. *Optimized PROD profile -> Filters*
	* Hostname to lowercase
	* Hostname example.cz
	* Exclude CyberFox Prague IP
	* Exclude local IPs
	* Aggregate source - facebook.com	
	* Exclude Language is (not set)
	* **!!! do not edit applied shared filter, it will change its original definition**
15. OPTIONAL: connect adWords
16. IMPORT from https://github.com/foxpress/GTM-default-container 

**-- OR --**

16. **GTM** -> Configure Built-In Variables + variables UA_ID a document.head.meta.robots
17. **GTM triggers,** see www.palmovkaopenpark.cz container
18. **GTM tags,** dtto
