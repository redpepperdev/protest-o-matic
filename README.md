# Protest-O-Matic
A bookmarklet that lets you throw foods on NFTs for your protest.

### Install
Go to your favorite browser's bookmark manager and create a new bookmark. Name it Protest-O-Matic, or whatever, and paste the very poorly written code below into the 'address' field. When you're ready to make a mess at your local NFT art gallery just click your bookmarklet and boom! Protest! 

DON'T FORGET YOUR SUPER GLUE!

```
javascript:(function(){
    var glued = 0;
    var count = 0;
    var o = 0.8;
    var i = 'potato.gif';
    var ts, x, y, p, val, hand, messy;
    function clicky(e){
        console.log('clicky');
        if(!glued && count > 4){
            document.body.innerHTML += '<img src="https://redpepper.land/wp-content/uploads/2022/10/hand.gif" style="position: fixed; right: 10px; top: 10px; z-index: 100001; pointer-events:none;">';
            glued = true;
        };
        count++;
        ts = new Date().getTime();
        x = e.clientX - 240;
        y = 0-(e.clientY - 670);
        var mess = document.createElement('img');
        mess.src = 'https://redpepper.land/wp-content/uploads/2022/10/'+i+'?'+ts;
        mess.style.cssText= 'position: fixed; left: '+x+'px; bottom: '+y+'px; opacity: '+o+';pointer-events:none;z-index:100000';
        document.getElementById('messy').appendChild(mess);
    };
    messy = document.createElement('div');
    messy.id = 'messy';
    messy.style.cssText = "position: fixed; top: 0;left:0;right:0;bottom:0; z-index:99999;";
    document.body.addEventListener('click', clicky, true);
    document.body.appendChild(messy);
    document.body.style.cursor = 'crosshair';
    document.body.innerHTML += '<select id="pick" style="position: fixed; right: 10px; bottom: 10px; z-index: 100002; font-size: 20px; padding:10px 20px; border: 1px solid black; background:white;font-family: Comic Sans MS; box-sizing:border-box;"><option value="potato">Liquified Buttery Mashed Potatoes</option><option value="pie">Pie</option></select>';
    document.getElementById('pick').addEventListener('change', function() {
        p = this.value;
        console.log(p);
        if(p=='potato'){
            i = 'potato.gif';
            o = 0.8;
        }else if(p=='pie'){
            i = 'pie.gif';
            o = 1;
        };
    });
})();
```
