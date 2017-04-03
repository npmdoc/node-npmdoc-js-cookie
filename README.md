# api documentation for  [js-cookie (v2.1.4)](https://github.com/js-cookie/js-cookie#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-js-cookie.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-js-cookie) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-js-cookie.svg)](https://travis-ci.org/npmdoc/node-npmdoc-js-cookie)
#### A simple, lightweight JavaScript API for handling cookies

[![NPM](https://nodei.co/npm/js-cookie.png?downloads=true)](https://www.npmjs.com/package/js-cookie)

[![apidoc](https://npmdoc.github.io/node-npmdoc-js-cookie/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-js-cookie_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-js-cookie/build..beta..travis-ci.org/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-js-cookie/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-js-cookie/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Klaus Hartl"
    },
    "bugs": {
        "url": "https://github.com/js-cookie/js-cookie/issues"
    },
    "dependencies": {},
    "description": "A simple, lightweight JavaScript API for handling cookies",
    "devDependencies": {
        "grunt": "1.0.0",
        "grunt-compare-size": "0.4.2",
        "grunt-contrib-connect": "1.0.2",
        "grunt-contrib-jshint": "1.1.0",
        "grunt-contrib-nodeunit": "1.0.0",
        "grunt-contrib-qunit": "1.3.0",
        "grunt-contrib-uglify": "2.2.1",
        "grunt-contrib-watch": "1.0.0",
        "grunt-jscs": "3.0.1",
        "grunt-saucelabs": "9.0.0",
        "gzip-js": "0.3.2",
        "qunitjs": "1.23.1",
        "requirejs": "2.3.3"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "da4ec503866f149d164cf25f579ef31015025d8d",
        "tarball": "https://registry.npmjs.org/js-cookie/-/js-cookie-2.1.4.tgz"
    },
    "gitHead": "8b70250875f7e07445b6a457f9c2474ead4cba44",
    "homepage": "https://github.com/js-cookie/js-cookie#readme",
    "keywords": [
        "jquery-plugin",
        "cookie",
        "cookies",
        "browser",
        "amd",
        "commonjs",
        "client",
        "js-cookie",
        "browserify"
    ],
    "license": "MIT",
    "main": "src/js.cookie.js",
    "maintainers": [
        {
            "name": "fagner",
            "email": "gravatar@fagnermartins.com"
        },
        {
            "name": "carhartl",
            "email": "klaus.hartl@gmail.com"
        }
    ],
    "name": "js-cookie",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/js-cookie/js-cookie.git"
    },
    "scripts": {
        "test": "grunt test"
    },
    "version": "2.1.4"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module js-cookie](#apidoc.module.js-cookie)
1.  [function <span class="apidocSignatureSpan">js-cookie.</span>get (key)](#apidoc.element.js-cookie.get)
1.  [function <span class="apidocSignatureSpan">js-cookie.</span>getJSON ()](#apidoc.element.js-cookie.getJSON)
1.  [function <span class="apidocSignatureSpan">js-cookie.</span>remove (key, attributes)](#apidoc.element.js-cookie.remove)
1.  [function <span class="apidocSignatureSpan">js-cookie.</span>set (key, value, attributes)](#apidoc.element.js-cookie.set)
1.  [function <span class="apidocSignatureSpan">js-cookie.</span>withConverter (converter)](#apidoc.element.js-cookie.withConverter)
1.  object <span class="apidocSignatureSpan">js-cookie.</span>defaults



# <a name="apidoc.module.js-cookie"></a>[module js-cookie](#apidoc.module.js-cookie)

#### <a name="apidoc.element.js-cookie.get"></a>[function <span class="apidocSignatureSpan">js-cookie.</span>get (key)](#apidoc.element.js-cookie.get)
- description and source-code
```javascript
get = function (key) {
			return api.call(api, key);
		}
```
- example usage
```shell
...
'''javascript
Cookies.set('name', 'value', { expires: 7, path: '' });
'''

Read cookie:

'''javascript
Cookies.get('name'); // => 'value'
Cookies.get('nothing'); // => undefined
'''

Read all visible cookies:

'''javascript
Cookies.get(); // => { name: 'value' }
...
```

#### <a name="apidoc.element.js-cookie.getJSON"></a>[function <span class="apidocSignatureSpan">js-cookie.</span>getJSON ()](#apidoc.element.js-cookie.getJSON)
- description and source-code
```javascript
getJSON = function () {
			return api.apply({
				json: true
			}, [].slice.call(arguments));
		}
```
- example usage
```shell
...
'''javascript
Cookies.get(); // => { name: '{"foo":"bar"}' }
'''

When reading a cookie with the 'Cookies.getJSON' api, you receive the parsed representation of the string stored in the cookie according
 to 'JSON.parse':

'''javascript
Cookies.getJSON('name'); // => { foo: 'bar' }
'''

'''javascript
Cookies.getJSON(); // => { name: { foo: 'bar' } }
'''

*Note: To support IE6-7 ([and IE 8 compatibility mode](http://stackoverflow.com/questions/4715373/json-object-undefined-in-internet
-explorer-8)) you need to include the JSON-js polyfill: https://github.com/douglascrockford/JSON-js*
...
```

#### <a name="apidoc.element.js-cookie.remove"></a>[function <span class="apidocSignatureSpan">js-cookie.</span>remove (key, attributes)](#apidoc.element.js-cookie.remove)
- description and source-code
```javascript
remove = function (key, attributes) {
			api(key, '', extend(attributes, {
				expires: -1
			}));
		}
```
- example usage
```shell
...
'''javascript
Cookies.get(); // => { name: 'value' }
'''

Delete cookie:

'''javascript
Cookies.remove('name');
'''

Delete a cookie valid to the path of the current page:

'''javascript
Cookies.set('name', 'value', { path: '' });
Cookies.remove('name'); // fail!
...
```

#### <a name="apidoc.element.js-cookie.set"></a>[function <span class="apidocSignatureSpan">js-cookie.</span>set (key, value, attributes)](#apidoc.element.js-cookie.set)
- description and source-code
```javascript
function api(key, value, attributes) {
			var result;
			if (typeof document === 'undefined') {
				return;
			}

			// Write

			if (arguments.length > 1) {
				attributes = extend({
					path: '/'
				}, api.defaults, attributes);

				if (typeof attributes.expires === 'number') {
					var expires = new Date();
					expires.setMilliseconds(expires.getMilliseconds() + attributes.expires * 864e+5);
					attributes.expires = expires;
				}

				// We're using "expires" because "max-age" is not supported by IE
				attributes.expires = attributes.expires ? attributes.expires.toUTCString() : '';

				try {
					result = JSON.stringify(value);
					if (/^[\{\[]/.test(result)) {
						value = result;
					}
				} catch (e) {}

				if (!converter.write) {
					value = encodeURIComponent(String(value))
						.replace(/%(23|24|26|2B|3A|3C|3E|3D|2F|3F|40|5B|5D|5E|60|7B|7D|7C)/g, decodeURIComponent);
				} else {
					value = converter.write(value, key);
				}

				key = encodeURIComponent(String(key));
				key = key.replace(/%(23|24|26|2B|5E|60|7C)/g, decodeURIComponent);
				key = key.replace(/[\(\)]/g, escape);

				var stringifiedAttributes = '';

				for (var attributeName in attributes) {
					if (!attributes[attributeName]) {
						continue;
					}
					stringifiedAttributes += '; ' + attributeName;
					if (attributes[attributeName] === true) {
						continue;
					}
					stringifiedAttributes += '=' + attributes[attributeName];
				}
				return (document.cookie = key + '=' + value + stringifiedAttributes);
			}

			// Read

			if (!key) {
				result = {};
			}

			// To prevent the for loop in the first place assign an empty array
			// in case there are no cookies at all. Also prevents odd result when
			// calling "get()"
			var cookies = document.cookie ? document.cookie.split('; ') : [];
			var rdecode = /(%[0-9A-Z]{2})+/g;
			var i = 0;

			for (; i < cookies.length; i++) {
				var parts = cookies[i].split('=');
				var cookie = parts.slice(1).join('=');

				if (cookie.charAt(0) === '"') {
					cookie = cookie.slice(1, -1);
				}

				try {
					var name = parts[0].replace(rdecode, decodeURIComponent);
					cookie = converter.read ?
						converter.read(cookie, name) : converter(cookie, name) ||
						cookie.replace(rdecode, decodeURIComponent);

					if (this.json) {
						try {
							cookie = JSON.parse(cookie);
						} catch (e) {}
					}

					if (key === name) {
						result = cookie;
						break;
					}

					if (!key) {
						result[name] = cookie;
					}
				} catch (e) {}
			}

			return result;
		}
```
- example usage
```shell
...
JavaScript Cookie can also be loaded as an AMD, CommonJS or [ES6](https://github.com/js-cookie/js-cookie/issues/233#issuecomment
-233187386) module.

## Basic Usage

Create a cookie, valid across the entire site:

'''javascript
Cookies.set('name', 'value');
'''

Create a cookie that expires 7 days from now, valid across the entire site:

'''javascript
Cookies.set('name', 'value', { expires: 7 });
'''
...
```

#### <a name="apidoc.element.js-cookie.withConverter"></a>[function <span class="apidocSignatureSpan">js-cookie.</span>withConverter (converter)](#apidoc.element.js-cookie.withConverter)
- description and source-code
```javascript
function init(converter) {
		function api (key, value, attributes) {
			var result;
			if (typeof document === 'undefined') {
				return;
			}

			// Write

			if (arguments.length > 1) {
				attributes = extend({
					path: '/'
				}, api.defaults, attributes);

				if (typeof attributes.expires === 'number') {
					var expires = new Date();
					expires.setMilliseconds(expires.getMilliseconds() + attributes.expires * 864e+5);
					attributes.expires = expires;
				}

				// We're using "expires" because "max-age" is not supported by IE
				attributes.expires = attributes.expires ? attributes.expires.toUTCString() : '';

				try {
					result = JSON.stringify(value);
					if (/^[\{\[]/.test(result)) {
						value = result;
					}
				} catch (e) {}

				if (!converter.write) {
					value = encodeURIComponent(String(value))
						.replace(/%(23|24|26|2B|3A|3C|3E|3D|2F|3F|40|5B|5D|5E|60|7B|7D|7C)/g, decodeURIComponent);
				} else {
					value = converter.write(value, key);
				}

				key = encodeURIComponent(String(key));
				key = key.replace(/%(23|24|26|2B|5E|60|7C)/g, decodeURIComponent);
				key = key.replace(/[\(\)]/g, escape);

				var stringifiedAttributes = '';

				for (var attributeName in attributes) {
					if (!attributes[attributeName]) {
						continue;
					}
					stringifiedAttributes += '; ' + attributeName;
					if (attributes[attributeName] === true) {
						continue;
					}
					stringifiedAttributes += '=' + attributes[attributeName];
				}
				return (document.cookie = key + '=' + value + stringifiedAttributes);
			}

			// Read

			if (!key) {
				result = {};
			}

			// To prevent the for loop in the first place assign an empty array
			// in case there are no cookies at all. Also prevents odd result when
			// calling "get()"
			var cookies = document.cookie ? document.cookie.split('; ') : [];
			var rdecode = /(%[0-9A-Z]{2})+/g;
			var i = 0;

			for (; i < cookies.length; i++) {
				var parts = cookies[i].split('=');
				var cookie = parts.slice(1).join('=');

				if (cookie.charAt(0) === '"') {
					cookie = cookie.slice(1, -1);
				}

				try {
					var name = parts[0].replace(rdecode, decodeURIComponent);
					cookie = converter.read ?
						converter.read(cookie, name) : converter(cookie, name) ||
						cookie.replace(rdecode, decodeURIComponent);

					if (this.json) {
						try {
							cookie = JSON.parse(cookie);
						} catch (e) {}
					}

					if (key === name) {
						result = cookie;
						break;
					}

					if (!key) {
						result[name] = cookie;
					}
				} catch (e) {}
			}

			return result;
		}

		api.set = api;
		api.get = function (key) {
			return api.call(api, key);
		};
		api.getJSON = function () {
			return api.apply({
				json: true
			}, [].slice.call(arguments));
		};
		api.defaults = {};

		api.remove = function (key, attributes) {
			api(key, '', extend(attributes, {
				expires: -1
			}));
		};

		api.withConverter = init;

		return api;
	}
```
- example usage
```shell
...
The returning String will be used as the cookie value.

Example from reading one of the cookies that can only be decoded using the 'escape' function:

'''javascript
document.cookie = 'escaped=%u5317';
document.cookie = 'default=%E5%8C%97';
var cookies = Cookies.withConverter(function (value, name) {
    if ( name === 'escaped' ) {
        return unescape(value);
    }
});
cookies.get('escaped'); // 北
cookies.get('default'); // 北
cookies.get(); // { escaped: '北', default: '北' }
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
