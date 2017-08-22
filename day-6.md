# LJ Code 301 - Day 6

## Article.fetchAll = function() {
  if (localStorage.rawData) {

    Article.loadAll(JSON.parse(localStorage.rawData));

    articleView.initIndexPage();

  } else {

    $.getJSON('data/hackeripsum.json').then(function(data) {

      localStorage.setItem('rawData', JSON.stringify(data));
      Article.loadAll(JSON.parse(localStorage.rawData));
    })
  }
}

## This process of parse ing if there is local storage to un stringify the data so we can display it, else if there is nothing in local storage get the data through json, stringify it, then parse it. This process was what we did in the lab, this is also how AJAX works.
