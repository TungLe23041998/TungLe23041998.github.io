var countries = {};


$.extend(countries, {
	US: {
		type: "buy",
		link: "https://www.samsung.com/us/smartwatches-and-fitness-bands/buy/s/Model/"
	}
});


$(function() {
	window.initBuyNowButtons = function() {

		var countryCode = $._cookie.get("country_codes");
		countryCode = (countryCode) ? $.trim(countryCode).toUpperCase() : "";
		var altTitles = {regist:"pre-registration", order:"pre-order", buy:"buy now"};
		var country = countries[countryCode] || {};


		if (country&&country.type) {
			$(".country-check")
			.addClass(country.type)
			.find(".order-button")
			.attr({href:country.link,target:"_blank",title:"Go to "+altTitles[country.type]+" page in a new window"})
			.off("click", GALAXY.tracking)
			.on("click", GALAXY.tracking)
		}
	};
});