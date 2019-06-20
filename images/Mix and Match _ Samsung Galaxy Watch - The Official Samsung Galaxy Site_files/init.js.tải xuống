var ___GALAXY_START_TIME = (new Date()).getTime();
var ___IS_GALAXY = (location.href.indexOf('/global/galaxy/')>-1||window.IS_CAMPAIGN===true) ? true : false;
(function() {
var width = document.documentElement.offsetWidth,
	sizeMode = width > 1440 ? 4 : width > 1023 ? 3 : width > 767 ? 2 : 1,
	html5tags = ['article', 'aside', 'details', 'figcaption', 'figure', 'footer', 'header', 'hgroup', 'nav', 'section', 'summary'],
	i = 0, max = html5tags.length;
for (i = 0; i < max; i++) document.createElement(html5tags[i]);
document.documentElement.className += (' s'+ sizeMode +' s'+ (3 > sizeMode ? 12 : 34) + (360 > width ? ' s0' : '')) + (___IS_GALAXY?'':' dotcom');
})();
