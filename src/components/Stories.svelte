
<style lang="scss">
  .stories {
    border: 1px solid rgba(219, 219, 219, 1);
    border-radius: 4px;
    margin: 1em 0;
    padding: 0.5em 1em;
    background-color: white;  
    &__item img {
      width: 32px;
      height: 32px;
      border-radius: 50%;
    }
    &__item {
      display: flex;
      align-items: center;
      margin: 0 0 0.5em 0;
    }
    &__item h2 {
      font-size: 14px;
      color: black;
      margin: 0 0 0 0.5em;
    }
    &__item h2 span {
      display: block;
      font-size: 9px;
      text-transform: uppercase;
      color: gray;
    }
    &__head {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0.5em 0 0 0;
    }
    &__head h2 {
      font-size: 12px;
      font-weight: 600;
    }
    &__head span {
      font-size: 12px;
      font-weight: normal;
      color: black;
    }
    &__items {
      margin: 0.5em 0 0.5em 0;
    }
    &__item-box {
      width: 32px;
      height: 32px;
      border: double 2px transparent;
      border-radius: 100%;
      background-image: linear-gradient(#fff, #fff),
        radial-gradient(circle at top left, #f09433, #bc1888);
      background-origin: border-box;
      background-clip: content-box, border-box;
    }
  }
</style>


<div class="stories">
    <div class="stories__container">
        <div class="stories__head">
            <h2>Stories</h2>
            <span>See all</span>
        </div>
        <div class="stories__items">
            <div class="stories__item">
                <div class="stories__item-box">
                    <img src="https://i.pinimg.com/originals/94/45/55/9445559841902dfdec9106f0d750ba69.jpg" />
                </div>
                <h2>Username
                  <span>10 hours ago</span>
                </h2>  
            </div>
             <div class="stories__item">
                <div class="stories__item-box">
                    <img src="https://i.pinimg.com/originals/94/45/55/9445559841902dfdec9106f0d750ba69.jpg" />
                </div>
                <h2>Username
                  <span>11 hours ago</span>
                </h2>  
            </div>
             <div class="stories__item">
                <div class="stories__item-box">
                    <img src="https://i.pinimg.com/originals/94/45/55/9445559841902dfdec9106f0d750ba69.jpg" />
                </div>
                <h2>Username
                  <span>15 hours ago</span>
                </h2>  
            </div>
        </div>
    </div>
</div>  