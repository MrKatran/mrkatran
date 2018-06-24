// ==UserScript==
// @name          VK community KPD & CPM counter
// @namespace     http://vk.com/
// @description
// @author        Andrey Karpitchev + meilleur.str
// @license       MIT
// @version       2.0
// @include       *vk.com/adsmarket*
// ==/UserScript==


function countKPDcpm() {

  tmp_tr = document.getElementById('exchange_comm_search_table').getElementsByTagName('tr');
  found_len = tmp_tr.length;

  for (var i = j; i < found_len-1; i++) {
    tmp_str = tmp_tr[i].getElementsByTagName('td')[3].innerHTML;
    tmp_str = tmp_str.replace(/<\/?[^>]+>/gi, '');
    tmp_str = tmp_str.replace(/[^\d\/]/gi, '');
    tmp_cpm = tmp_tr[i].getElementsByTagName('td')[4].innerHTML;
    tmp_cpm = tmp_cpm.replace(/<\/?[^>]+>/gi, '');
    tmp_cpm = tmp_cpm.replace(/[^\d\/]/gi, '');

    found = tmp_str.match(/(\d+)\/(\d+)/);
    found_cpm = tmp_cpm.match(/(\d+)/);

    if (found) {
      tmp_kpd = found[1]/found[2]*100;
      tmp_cpm = found[3]*1;
      font_color = (tmp_kpd>=10) ? 'orange' : 'red';
      if (tmp_kpd>=20) font_color = 'green';
      tmp_tr[i].getElementsByTagName('td')[3].innerHTML += '<br/><b>КПД: <font color="' + font_color + '">' +tmp_kpd.toFixed(2) + '%</font></b>';

      if (found_cpm) {
      tmp_cpm = found_cpm[1]/found[1]*1000;
      font_color = 'blue';
      if (tmp_cpm<=30) font_color = 'green';
      if (tmp_cpm>=50) font_color = 'red';
      tmp_tr[i].getElementsByTagName('td')[4].innerHTML += '<br/><b>CPM: <font color="' + font_color + '">' +tmp_cpm.toFixed(2) + ' руб</font></b>';

}

    }
  }

  j = found_len-1;

  // repeat
  setTimeout(countKPDcpm, 1500);
}

j = 1;

// count
countKPDcpm();
