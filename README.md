# NextJs

### index File
>src/pages/index.js.js
```js
import Head from "next/head";
import Link from "next/link";

function HomePage() {
    return <>
        <Link href={'User/'} className={'btn btn-md rounded btn-primary'}>Go</Link>
    </>
}

export default HomePage
```

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
