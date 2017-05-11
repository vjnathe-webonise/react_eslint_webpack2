# react_eslint_webpack2
ESLint webpack configuration to work against React

1) we need parser that will be used along the ESLint to indentify JSX, this will be installed with compatible version of ESLint:

npm install eslint@3.x babel-eslint@6 --save-dev

2) installe eslint loader that will be used under webpack config:

npm install eslint-loader --save-dev

3) add '.eslintrc' file at root for eslint configuration:

{
  "parser": "babel-eslint",
  "rules": {
    "no-dupe-keys": 2,
    "no-cond-assign": 2,
    "no-sparse-arrays": 2,
    "eqeqeq": 1,
    "radix": 1,
    "no-unused-vars": 1
  }
}

For more rules of ESLint REF: http://eslint.org/docs/rules/
2: Error, 1: Warning, 0: No Error

3) In webpack(2) configuration add under rules(loaders):

{
    enforce: "pre",
    test: /\.js$/,
    exclude: [/node_modules/,/vendor/],
    loader: "eslint-loader"
}
