window.wsg_base_url = 'https://www.improvedcontactform.com';

function wsg_inject_script(url, cb) {
  var sc = document.createElement('script');
  sc.type = 'text/javascript';
  sc.src = url;
  sc.async = true;

  if (typeof cb === 'function')
    sc.onload = sc.onreadystatechange = cb;

  var first = document.getElementsByTagName('script')[0];
  first.parentNode.insertBefore(sc, first);
}

//load jquery if not already present, then continue
(function( window, document, callback, $, script, done, readystate ){
  //'1.12.4' > $.fn.jquery || 
  if (!($ = window.jQuery) || typeof $.fn.on === 'undefined' || callback($)) {
    wsg_inject_script('https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js', function() {
      if (!done && (!(readystate = this.readyState) || readystate == 'loaded' || readystate == 'complete')) {
        window.$J = jQuery.noConflict(true);
        callback($J, done = 1);
      }
    });
  }
}(window, document, function($) {

  window.$J = $;

  //don't run twice
  if (typeof window.wsg_options !== 'undefined' && window.wsg_options.length) return;

  $('<link/>', {
     rel: 'stylesheet',
     type: 'text/css',
     href: window.wsg_base_url + '/css/widget.css'
  }).appendTo('head');

  wsg_inject_script(window.wsg_base_url + '/js/widgets.js');

  //demo/preview
  $('script').each(function() {    
    if ($(this).data('wsg-id')) {
      var url = window.wsg_base_url + '/ws/loader/?id=' + $(this).data('wsg-id');
      if (typeof window.wsg_widget_id !== 'undefined') {
        url += '&widget_id=' + window.wsg_widget_id;
      }
      wsg_inject_script(url);
    }
  });

  if (typeof window._w3counter !== 'undefined') {
    var url = window.wsg_base_url + '/ws/loader/?w3counter_id=' + window._w3counter;
    if (typeof window.wsg_widget_id !== 'undefined') {
      url += '&widget_id=' + window.wsg_widget_id;
    }
    wsg_inject_script(url);
  }

  if (typeof Shopify !== 'undefined' && typeof Shopify.shop !== 'undefined') {
    var url = window.wsg_base_url + '/ws/loader/?shop=' + Shopify.shop;
    if (typeof window.wsg_widget_id !== 'undefined') {
      url += '&widget_id=' + window.wsg_widget_id;
    }
    wsg_inject_script(url);
  }

}));