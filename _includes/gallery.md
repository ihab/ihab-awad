<style type="text/css">
    .gallery-container {
        margin-left: 50px;
        display: flex;
    }
    .gallery-img {
        max-width: 150px;
        max-height: 150px;
        border-radius: 5px;
    }
    .gallery-entry {
      text-align: center;
      margin: 10px;
      padding: 5px;
      transition: border 0.5s ease, box-shadow 0.5s ease;
      border-radius: 5px;
      border: 2px solid #ffffff;
    }
    .gallery-entry:hover {
      border: 2px solid #f0f0f0;        
      box-shadow: 3px 3px 0px 0px #e0e0e0;
    }
</style>

<p>
    <div class="gallery-container">
        {% for img in imgs %}
            <div class="gallery-entry">
                <a href="{{ img }}">
                    <img src="{{ img }}" class="gallery-img">
                </a>
            </div>
        {% endfor %}
    </div>
</p>