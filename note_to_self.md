* To test the site locally. Start Docker and run docker compose up.

* To modify layouts of the items on the main page, go to _layouts\bib.html
* To modify fun facts, go to _includes\footer.html
* Style files: Under _sass

* Image template
```
    <figure>
        <picture class="tldr_img">
        <img
            src="/assets/img/gaggia.jpg"
            width="50%"
            onerror="this.onerror=null; $('.responsive-img-srcset').emove();"
        />
        </picture>
      </figure>
``````