# NextJs
### Env File
>.env.local [root leve]
```shell
NEXT_PUBLIC_SOMETHING=12345
TEST=12
```
and to get data from it
```
process.env.TEST
```
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
### Document file
>src/pages/index.js.js
```js
import { Html, Head, Main, NextScript } from 'next/document'

export default function Document() {
    return (
        <Html>
            <Head />
            <body>
            <Main />
            <NextScript />
            </body>
        </Html>
    )
}
```
### Permit external js
>next.config.js
```js
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    urlImports: ['https://cdn.jsdelivr.net/gh/anupam-dixit/'],
    appDir: false,
  },
}

module.exports = nextConfig
```
