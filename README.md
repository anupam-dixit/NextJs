# NextJs
### Universal Project Imports
>src/pages/_app.js
create file if doesnt exist.
```js
import "/src/mdb/css/mdb.min.css";
import "/src/mdb/css/admin.css";
import {useEffect} from "react";

function MyApp({ Component, pageProps }) {

    useEffect(() => {
        require('/src/mdb/js/mdb.min.js');
        require('/src/mdb/js/admin.js');
    }, []);
    return (
            <Component {...pageProps} />
    );
}

export default MyApp;

```
