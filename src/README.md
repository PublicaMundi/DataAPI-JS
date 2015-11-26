Data API allows users to query any resource that has been added to the catalog using the PublicaMundi Vector Storer extension.
<br/><br/>
Data can be queried using an instance of {@link module:PublicaMundi.Data.Query Query} class.
<br/><br/>
Available resources can be retrieved using the {@link module:PublicaMundi.Data.Query#getResources getResources} function.
<br/><br/>
Details about a resource, its fields and geometry CRS can be obtained by calling {@link module:PublicaMundi.Data.Query#describeResource describeResource} function.

    var query = new PublicaMundi.Data.Query('path/to/service/endpoint/');

    query.resource('cities', 'table1').
        greater({name : 'h'}, 100).
        orderBy('h', true).
        skip(20).
        take(50);

    query.execute({
        success: onSuccess,
        failure: onFailure,
        complete: onComplete
    });
