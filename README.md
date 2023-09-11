Enlodi Axios istek tipleri
Genellikle 2.yöntem tavsiye edilir.


📌1.Yöntem

axios.get('{{ route('admin.product.view') }}', productId, {
    headers: {
        'Content-Type': 'application/json',
    }
})

ℹ️Bu istek, URL'ye productId'yi ekler. Özellikle tek bir ürünün ayrıntılarına erişmek için kullanışlıdır. Örneğin, eğer bir e-ticaret sitesinde bir ürünün ayrıntılarını görüntülemek istiyorsanız ve bu ürünün ID'sini kullanıyorsanız, bu yöntemi tercih edebilirsiniz. Headers bölümünde 'Content-Type' başlığını belirterek gönderilen verinin JSON olduğunu belirtiyorsunuz. 


📌2.Yöntem

axios.get('{{ route('admin.product.view') }}', {
    id: rowId
})

ℹ️Bu istek, id'yi URL'ye ekler. Bu, daha genel bir kaynağa erişmek veya bir kaynağı filtrelemek için kullanışlıdır. Örneğin, tüm ürünleri listelemek veya belirli bir kategoriye ait ürünleri listelemek için kullanabilirsiniz. Bu şekilde parametreler daha açık ve okunaklıdır.


📌3.Yöntem
axios({
    method: 'get',
    url:'{{route('admin.product.view')}}' + '/' + id,
    data: formData,
    responseType: 'json',
})

Bu istek, daha genel bir kullanım sunar. HTTP methodunu, URL'yi, gönderilecek veriyi (formData) ve yanıtın nasıl işleneceğini (responseType) ayrı ayrı belirlemenizi sağlar. Bu, özellikle isteğin karmaşıklığı arttığında veya özelleştirilmiş istekler yapmanız gerektiğinde kullanışlıdır. Ancak, bu isteğin URL oluşturma yöntemi diğerlerine göre daha karmaşıktır.
