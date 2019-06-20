adroll_adv_id = '';
adroll_pix_id = '';

(function () {
    function parseQuery(query) {
        var Params = new Object();
        if (!query) return Params;
        var Pairs = query.split(/[;&]/);
        for (var i = 0; i < Pairs.length; i++) {
            var KeyVal = Pairs[i].split('=');
            if (!KeyVal || KeyVal.length != 2) continue;
            var key = decodeURIComponent(KeyVal[0]);
            var val = decodeURIComponent(KeyVal[1]);
            val = val.replace(/\+/g, ' ');
            Params[key] = val;
        }
        return Params;
    }

    var scripts = document.getElementsByTagName('script');
    for(var i = 0; i < scripts.length; i++){
        var script = scripts[i];
        if (script.src && script.src.indexOf('shopify_rolling_bootstrap') != -1) {
            var queryString = script.src.replace(/^[^\?]+\??/, '');
            var params = parseQuery(queryString);
            adroll_adv_id = params.adroll_adv_id;
            adroll_pix_id = params.adroll_pix_id;
            break;
        }
    }

    adroll_version = '2.0';

    (function(w,d,e,o,a){
        w.__adroll_loaded=true;
        w.adroll=w.adroll||[];
        w.adroll.f=['setProperties','identify','track'];
        var roundtripUrl = 'https://s.adroll.com/j/' + adroll_adv_id + '/roundtrip.js';
        for(a=0;a<w.adroll.f.length;a++){
            w.adroll[w.adroll.f[a]]=w.adroll[w.adroll.f[a]]||(function(n){return function(){w.adroll.push([n,arguments])}})(w.adroll.f[a])};e=d.createElement('script');o=d.getElementsByTagName('script')[0];e.async=1;e.src=roundtripUrl;o.parentNode.insertBefore(e, o);})(window,document);
}());
