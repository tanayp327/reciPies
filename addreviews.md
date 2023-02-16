---
permalink: /addreview/
title: Add Review
---

<style>
    body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
    }
    body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
    }
    .search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin: 10px auto;
    position: absolute;
    top: 20px;
    left: 50%;
    transform: translate(-50%, 0);
    }
    .container {
    position: relative;
    text-align: center;
    color: black;
    }
    .bottom-right {
    position: absolute;
    bottom: 8px;
    right: 16px;
    background-color: #ffffff;
    }
</style>




<h2>Leave a Comment & Rating</h2>

<form action="/reviews">
  <label for="rating">Rating</label><br>
  <input type="text" id="rating" placeholder="Rate out of 10">
  <label for="comment">Comment</label><br>
  <textarea rows="8" id="comment" placeholder="Add a short comment about your experience with this recipe" style="width:619px"></textarea>
  <label for="name">Name</label><br>
  <input type="text" id="name">
  <label for="email">Email</label><br>
  <input type="text" id="email">
  <button type="submit" value="Post Comment" onclick="postComment()">Submit</button>
</form> 

<script>
    function postComment() {
        let request2 = new XMLHttpRequest()
        // request2.open("POST", "https://lyntax.ml/api/keypress") //uncomment for final
        request2.open("POST", "/api/review")
        request2.setRequestHeader('Content-Type', 'application/json');
        const obj = {'context':context,'key':key};
        const myJSON = JSON.stringify(obj);
        request2.send(myJSON)