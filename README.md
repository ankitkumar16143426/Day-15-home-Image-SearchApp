# Day-15-home-Image-SearchApp
In the html part  we take a  div that's class is search result and take a  button that's name show more after  that we apply basic css 
property as  like css flex box , hover effert and give the backgound color.
In the Java Script create a access key and apply querySelector at ("form")    :- (const formEl = document.querySelector("form"); )
after that get the all element by using document.getElementById method
and create a function async function :-  async function searchImages()
after the fect the API and api responce to convert to Json :-
       const response = await fetch(url);
       const data = await response.json();
and store the resopne into data and apply the map function on result :-
 results.map((result) => {
    const imageWrapper = document.createElement("div");
    imageWrapper.classList.add("search-result");
    const image = document.createElement("img");
    image.src = result.urls.small;
    image.alt = result.alt_description;
    const imageLink = document.createElement("a");
    imageLink.href = result.links.html;
    imageLink.target = "_blank";
    imageLink.textContent = result.alt_description;
After that appendChild the all child :-
       imageWrapper.appendChild(image);
       imageWrapper.appendChild(imageLink);
      searchResultsEl.appendChild(imageWrapper);
      
Add apply addEventListener funcion on submit event ie:-
   formEl.addEventListener("submit", (event) => {
    event.preventDefault();
    page = 1;
    searchImages();
    });

    showMoreButtonEl.addEventListener("click", () => {
    searchImages();
});
