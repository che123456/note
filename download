if (window.navigator.msSaveBlob) {
    // for ie 10 and later
    try {
      let blob = new Blob([data.data]);
      window.navigator.msSaveBlob(blob, fileName);
    } catch (e) {
      console.log(e);
    }
  } else {
    let url = window.URL.createObjectURL(data.data);
    let link = document.createElement('a');
    link.style.display = 'none';
    link.href = url;
    link.setAttribute('download', fileName);
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }
