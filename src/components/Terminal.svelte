<script lang="ts">
import feather from 'feather-icons';
export let author: string;
let formattedAuthor = author
  .replaceAll('ä', 'a')
  .replaceAll('ö', 'o')
  .replaceAll('å', 'a')
  .replaceAll(' ', '.')
  .toLocaleLowerCase();
</script>

<div id="terminal-container">
  <div id="top-bar-container">
    <div class="bar">guest@portfolio: /home/{formattedAuthor}</div>
    <div class="close-button">
      {@html feather.icons.x.toSvg({
        width: '25px',
        "stroke-width": '3px',
        height: '25px'
      }) }
    </div>
  </div>
  <div id="terminal-content-container">
    <slot></slot>
  </div>
</div>

<style lang="scss">
#terminal-container {
  width: 100%;
  max-width: var(--content-max-width);
  border: 2px solid rgb(0, 217, 255);
  background-color: #002c5fdd;
}

#terminal-content-container {
  padding: 10px;
}

#top-bar-container {
  display: flex;
  flex-direction: row;
  margin: 0;

  background: linear-gradient(90deg, rgb(0, 108, 196) 24%, rgb(0, 80, 146) 100%);

  border: 1px solid rgb(0, 80, 11);

  .bar {
    flex-grow: 1;
    color: var(--default-text-color);
    font-size: small;
    display: flex;
    align-items: center;
    padding-left: 5px;
    font-family: monospace;
  }

  .close-button {
    height: 25px;
    width: 25px;
    color: var(--default-text-color);
  }
}
</style>