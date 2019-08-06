"use strict";
function ajaxfilter(url){
  var urlparam = getSearchParams(),
      urlparam = $.param( urlparam );

  if(urlparam){
    var splite_url = url.split('?');
    url = splite_url[0]+"?"+urlparam;
  }

  $.ajax({
    type: 'GET',
    url: url,
    data: {},
    beforeSend:function(){
      $('body').addClass('loading hideOverly');
    },
    complete: function (data) {

      $('.productList').html($(".productList", data.responseText).html());
      $('.sidebar_tags').html($(".sidebar_tags", data.responseText).html());
      check_filters();
      productGrid();
      gridAddToCart();
      $('#pagination').remove();
      $('.pagination').html($(".pagination", data.responseText).html());
      if(!$(".pagination", data.responseText).html()){
        $('.pagination').hide();
      } else {
        $('.pagination').show();
      }
      $('body').removeClass('loading hideOverly');

      if($(".spr-badge").length > 0) {
        $.getScript(window.location.protocol + "//productreviews.shopifycdn.com/assets/v4/spr.js");
      }
      
      $('.btn-filter').click(function(){
         $(".filterbar").toggleClass("active");
      });

      history.pushState({
        page: url
      }, url, url);
    }
  });
}
    
function gridAddToCart() {
  $(".add-to-cart").click(function(i) {
    i.preventDefault();
    if (theme.ajax_cart) {
      var att = $(this).attr("id"),
          qty = $(this).attr("rel");
      addinToCart(att, qty);
    } else {
      $(this).parent().submit();
    }
    return;
  });
}

function addinToCart(att, qty ) {
  $("body").addClass("loading");
	CartJS.addItem(att, qty, {
  },
  {
    "success": function(data, textStatus, jqXHR){
      $("#successDrawer").find(".modal-prod-img").attr("src", data.image);
      $("#successDrawer").find(".modal-prod-img").load(function() {

        $("body").removeClass("loading");

        $("#successDrawer").find(".modal-prod-name").text(data.product_title),
          $("#successDrawer").find(".wishlistTxt").hide(),
          $("#successDrawer").find(".cartText").show(),

          $("body").addClass("showOverly"),$("#successDrawer").fadeIn(500), drawerTimeout = setTimeout(function() {
          $("body").removeClass("showOverly"), $("#successDrawer").fadeOut(500)
        }, 8000);
      });
    },
    "error": function(jqXHR, textStatus, errorThrown){
      var errormsg = JSON.parse(jqXHR.responseText).description;
      $("body").removeClass("loading");
      $(".error-message").text(errormsg);
      $("body").addClass("showOverly"),$("#errorDrawer").fadeIn(500), drawerTimeout = setTimeout(function() {
        $("body").removeClass("showOverly"), $("#errorDrawer").fadeOut(500)
      }, 8000);
    }
  });
}

function productGrid() {
  var gridRows = []; 
  var tempRow = [];

  productGridElements = $('.productList .grid-products .grid__item');
  productGridElements.each(function (index) {
    if ($(this).css('clear') != 'none' && index != 0) {
      gridRows.push(tempRow);
      tempRow = []; 
    }
    tempRow.push(this);

    if (productGridElements.length == index + 1) {
      gridRows.push(tempRow);
    }
  });

  $.each(gridRows, function () {
    var tallestHeight = 0;
    var tallestHeight1 = 0;
    $.each(this, function () {
      $(this).find('.grid-view_image a.grid-view-item__link').css('height', '');

      elHeight = parseInt($(this).find('.grid-view_image').css('height'));

      if (elHeight > tallestHeight) { tallestHeight = elHeight; }
    });
	
    $.each(this, function () {
      var gridImg = $(this).find('.grid-view_image .grid-view-item__image');
      if($(window).width() > 750) {
        $(gridImg).load(function() {
        	$(this).find('.grid-view_image > a.grid-view-item__link').css('height', tallestHeight);
        });
      }
    });
  });
}

function getSearchParams(k){
  var p={};
  location.search.replace(/[?&]+([^=&]+)=([^&]*)/gi,function(s,k,v){p[k]=v})
  return k?p[k]:p;
}