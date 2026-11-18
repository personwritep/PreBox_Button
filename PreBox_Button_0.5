// ==UserScript==
// @name        PreBox Button
// @namespace        http://tampermonkey.net/
// @version        0.5
// @description        ウェブページ掲載の「preタグ」内のコードをコピーする
// @author        Ameblo User
// @match        https://*/*
// @icon        https://www.google.com/s2/favicons?sz=64&domain=ameba.jp
// @noframes
// @grant        GM_setClipboard
// @updateURL        https://github.com/personwritep/PreBox_Button/raw/main/PreBox_Button.user.js
// @downloadURL        https://github.com/personwritep/PreBox_Button/raw/main/PreBox_Button.user.js
// ==/UserScript==


let pbop_host=null;
let pbop_sw=null;
let current_pre_elem=null;


function menu_set(){ // ボタンとShadow DOMを生成
    if(pbop_host) return;

    pbop_host=document.createElement('div'); // ホスト要素を作成、外部CSSの継承をリセット
    pbop_host.style.all='initial';

    let shadow=pbop_host.attachShadow({ mode: 'closed' }); // 'closed' モードでShadow DOM作成

    let style=document.createElement('style');
    style.textContent=`
        .pbop_sw {
            font: bold 16px Meiryo; position: absolute; display: none; z-index: 2147483647;
            padding: 3px 8px 1px; text-align: right; border: 1px solid #fff; border-radius: 4px;
            color: #fff; background: #0288d1; box-shadow: 4px 4px 2px -2px rgba(0, 0, 0, 0.5);
            cursor: pointer; white-space: nowrap; }
        .pbop_sw:hover {
            background: #1565c0; }
        .svg_cp {
            width: 20px; height: 16px; vertical-align: -2px; fill: #fff; }
    `;

    pbop_sw=document.createElement('div');
    pbop_sw.className='pbop_sw';

    let span=document.createElement('span');
    span.textContent='Copy code ';
    pbop_sw.appendChild(span);

    let svgNS='http://www.w3.org/2000/svg'; // SVG構築（Trusted Types/CSPブロックを回避）
    const svg=document.createElementNS(svgNS, 'svg');

    svg.setAttribute('class', 'svg_cp');
    svg.setAttribute('viewBox', '0 0 16 16');

    let path1=document.createElementNS(svgNS, 'path');
    let d1=
        'M0 6.8C0 5.8 .8 5 1.8 5h1.5a0.8 .8 0 0 1 0 1.5h-1.5a0.3 .3 0 0 '+
        '0-0.3 .3v7.5c0 .138.112.25.25.25h7.5a0.3 .3 0 0 0 0.3-0.3v-1.5a0.8 .8 0 '+
        '0 1 1.5 0v1.5A1.8 1.8 0 0 1 9.3 16h-7.5A1.8 1.8 0 0 1 0 14.3Z';
    path1.setAttribute('d', d1);

    let path2=document.createElementNS(svgNS, 'path');
    let d2=
        'M5 1.8C5 0.8 5.8 0 6.8 0h7.5C15.2 0 16 0.8 16 1.8v7.5A1.8 1.8 0'+
        ' 0 1 14.3 11h-7.5A1.8 1.8 0 0 1 5 9.3Zm1.8-0.3a0.3 .3 0 0 0-0.3 .3v7.5c0'+
        ' .138.112.25.25.25h7.5a0.3 .3 0 0 0 0.3-0.3v-7.5a0.3 .3 0 0 0-0.3-0.3Z';
    path2.setAttribute('d', d2);

    svg.appendChild(path1);
    svg.appendChild(path2);
    pbop_sw.appendChild(svg);

    pbop_sw.addEventListener('click', function(event){
        event.stopImmediatePropagation();
        if(current_pre_elem){
            get_copy(current_pre_elem, pbop_sw); }});

    shadow.appendChild(style); // Shadow DOM に格納して body へ追加
    shadow.appendChild(pbop_sw);
    document.body.appendChild(pbop_host);

} // menu_set()


menu_set();
document.addEventListener('click', set_range);

function set_range(event){
    if(event.target===pbop_host) return;

    let body=document.body;
    let zoom_f=parseFloat(window.getComputedStyle(body).getPropertyValue('zoom')) || 1;

    if(pbop_sw){
        let path=event.composedPath();
        let pre_elem=path.find(
            (el)=>el instanceof HTMLElement && (el.tagName==='PRE' || el.tagName==='CODE'));

        if(pre_elem && event.ctrlKey){
            pbop_sw.style.display='block';
            pbop_sw.style.left=(event.pageX / zoom_f) + "px";
            pbop_sw.style.top=((event.pageY / zoom_f) - 34) + "px";

            let selection=document.getSelection();
            let range=document.createRange();
            range.selectNodeContents(pre_elem);
            selection.removeAllRanges();
            selection.addRange(range);

            current_pre_elem=pre_elem; }
        else{
            pbop_sw.style.display='none';
            current_pre_elem=null; }}

} // set_range()


function get_copy(preb, sw){
    let sw_span=sw.querySelector('span');
    if(navigator.clipboard){
        navigator.clipboard.writeText(preb.textContent)
            .then(function(){
            sw_span.textContent='Copied　　';
            setTimeout(()=>{
                sw.style.display='none';
            }, 1500);
            setTimeout(()=>{
                sw_span.textContent='Copy code ';
            }, 1500);
        }); }

} // get_copy()
