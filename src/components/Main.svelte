<script>
  import Card from "./Card.svelte";
  import Taps from './Taps.svelte'
  import {fade, slide} from 'svelte/transition'

  let taps = ['شلالات', 'جلسات خارجية', 'مظلات سيارات', 'نخل واشنطون','أحواض زراعه','السطح','تحت الدرج']
  const activeTapInfo = {
        'أحواض زراعه': [36, 'a7owad'],
        'السطح': [8, 'roof'],
        'الفناء الخارجي': [20, 'outside'],
        'تحت الدرج': [13, 'under'],
        'شلالات': [20, 'fall'],
        'مظلات سيارات': [17, 'cars'],
        'نخل واشنطن': [9,'trees'],
    }
  let activeTap = 'مظلات سيارات';
  let n = activeTapInfo[activeTap][0]
  let name = activeTapInfo[activeTap][1]

  const tapChange = (e) => {
    activeTap = e.detail;
    arr = makeArray(n);
  }

  const makeArray = (n) => {
        return new Array(n)
    }
    let arr = makeArray(activeTapInfo[activeTap][0]);
    console.log(arr)
</script>

<main>
  <div class="title">
    <h1>أمتلك أفضل الحدائق</h1>
  <p>إذا كنت تمتلك حديقة بمنزلك، وترغب في إعادة تصميمها وتحويلها إلى تحفة فنية، فلا ترهق نفسك بالبحث كثيرا عن  أفضل شركات تنسيق حدائق،  وذلك لأن  <span>الهادي</span> من أشهر الشركات التي تبتكر تصميمات خاصة بتنسيق الحدائق.
  </p>
  <button><a href="https://www.tiktok.com/@tnsiq_hdayq?_t=8iR1Ja2MPIL&_r=1 " target="_blank">Tik Tok</a></button>
  </div>
  <Taps {taps} {activeTap} on:tapChange={tapChange} />
  {#if activeTap === 'مظلات سيارات'}
  <div transition:slide>
    <Card arr= {new Array(13)} name='cars'/>
  </div>
  {:else if activeTap === 'شلالات'}
    <div transition:slide>
    <Card arr={new Array(20)}  name='fall'/>
    </div>
  {:else if activeTap === 'نخل واشنطون'}
  <div transition:fade>
    <Card arr={new Array(9)}  name='trees'/>
  </div>
  {:else if activeTap === 'السطح'}
  <div transition:slide>
    <Card arr={new Array(2)}  name='roof'/>
  </div>
  {:else if activeTap === 'جلسات خارجية'}
  <div transition:fade>
    <Card arr={new Array(14)}  name='outside'/>
  </div>
  {:else if activeTap === 'تحت الدرج'}
  <div transition:slide>
    <Card arr={new Array(13)}  name='under'/>
  </div>
  {:else if activeTap === 'أحواض زراعه'}
  <div transition:fade>
    <Card arr={new Array(36)}  name='a7owad'/>
  </div>
  {/if} 
  
</main>

<style>
  a {
    text-decoration: none;
  }
  a , a:active, a:visited {
    color: #29ab87;
  }
  .title {
    max-width: 660px;
    margin: 0 auto;
    text-align: center;
  }
  p {
    font-size: 1.2rem;
  }
  span {
    color: #29ab87;
    font-weight: bold;
    font-size: 1.5rem;
  }
  button {
    border-radius: .8rem;
    padding: .5rem 1rem;
    font-size: 1.2rem;
    cursor: pointer;
    transition: all .5s ease;
    border: none;
    text-align: center;
    background-color: #252525;
    
  }
  button:hover {
    background-color: #29ab87;
    
  }
  button:hover a  {
    color: white;
  }

</style>