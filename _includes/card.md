<style type="text/css">
    .xcard {
      text-align: center;
      margin: 10px;
      padding: 5px;
      /* width: 150px; */
      /*
      # background-color: #e0e0e0;
      # border-color: #303030;
      # border-width: 1px;
      # border-style: solid;
      # border-radius: 5px;
      */
      transition: border 0.5s ease, box-shadow 0.5s ease;
      border-radius: 5px;
      border: 2px solid #ffffff;
    }
    .xcard:hover {
      border: 2px solid #f0f0f0;        
      /* background-color: #f0f0f0; */
      box-shadow: 3px 3px 0px 0px #e0e0e0;
    }
    .xcard-title {
      display: inline-block;
      width: fit-content;
    }

</style>

{% assign img_url = entry.link | append: "/icon.png" %}

<div class="xcard">
  <a href="{{ entry.link }}/index.html">
    <div><img src="{{ img_url }}" width="64px" height="64px"></div>
    <div class="xcard-title">{{ entry.title }}</div>
  </a>
</div>
