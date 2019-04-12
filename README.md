# Configuracion basica para React 16 y Webpack 4

#### 1. $ npm init -y
#### 2. $ npm install react react-dom
#### 3. $ npm install --save-dev webpack webpack-dev-server webpack-cli
#### 4. $ npm install -D babel-loader @babel/core @babel/preset-env @babel/preset-react html-webpack-plugin
#### 5. $ npm install style-loader css-loader --save-dev
#### 6. Configuración de archivo webpack.config.js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
    entry: './src/index.js',
    output: {
        path: path.join(__dirname, '/dist'),
        filename: 'index_bundle.js'
    },

    devServer: {
        port: 5000
    },
    module: {
        rules: [
            {
                test: /\.js$/,
                exclude: /node_modules/,
                use: {
                    loader: 'babel-loader'
                }
            },
            // Css
            {
                test: /\.css$/,
                use: [
                    { loader: 'style-loader' }, 
                    { loader: 'css-loader' }
                ]
            }
        ]
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: './src/index.html'
        })
    ]
}

#### 7. Creación de archivo .babelrc en la raíz del proyecto

{
   "presets": ["@babel/preset-env", "@babel/preset-react"]
}

#### 8. Empezar a crear componentes en React

#### 9. Run Server
$ npm start

#### 10. Producción
$ npm run build
