ちょっとしたものはCDNからvue.jsを読み込むだけでいいが、   
本格的な開発をするならvue-cli

# Installation
```bash
# vuetify使うためversionを落とす
sudo npm install -g @vue/cli@3.5.1
vue --version
# vue 3
vue create vue-app
# vue 2  template_type : webpack or webpack-simple or browserify or browserify-simple or pwa or simple 
vue init [template_type] vue-app
```

# 開発時
```bash
npm run serve
```
localhost:8080でアクセスする

# 配布するときはDeploy
```bash
npm run build
```

# Vuetify Plugin
Vue.jsのBootstrapみたいなもの

```bash
vue add vuetify
```
