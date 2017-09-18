# A simple html boilerplate 

We're doing a parallax tutorial in JS. 

For this tutorial, we will:

* Make the background scroll slowly for a parallax effect
* add key event listeners for left and right buttons
* do a fetch to replay the "important text

To complete the tutorial you'll want to add a `script.js` file and have this code in there. 

(try following the tutorial without looking at the answer code below)

<p><details>
  <summary><b>script.js</b></summary>
  <pre>

    let body = document.querySelector('body')
    let container = document.querySelector('.container')

    let scrollHandler = e => {
      const scrollPos = e.target.scrollLeft
      body.style.backgroundPositionX = (-0.1*scrollPos) + "px";
    }

    let keyHandler = e => {
      const width = e.target.clientWidth
      const currentPage = Math.floor(container.scrollLeft/width);

      switch (e.keyCode) {
        case 39:
          const nextPage = currentPage+1;
          container.scrollLeft = nextPage*width
          break
        case 37:
          const prevPage = currentPage-1;
          container.scrollLeft = prevPage*width
          break
      }
    }

    container.addEventListener('scroll', scrollHandler)
    body.addEventListener('keydown', keyHandler)

  </pre>
</details></p>