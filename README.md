#1 npm init

#2 npm install webpack webpack-cli webpack-dev-server rimraf copy-webpack-plugin --save-dev

#3 crear en la raiz del proyecto un webpack.config.js file

const path = require('path');
const CopyPlugin = require('copy-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'index.js',
    path: path.resolve(__dirname, 'dist'),
  },
  devServer: {
    contentBase: path.join(__dirname, 'dist'),
    compress: true,
    port: 9000
  },
  plugins: [
    new CopyPlugin({
      patterns: [
        { from: 'src/index.html', to: '' },
      ],
    }),
  ],
};

#4 npm install -g webpack-dev-server
