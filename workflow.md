1. 克隆仓库 
    ```
    - name: checkout opencv
        uses: actions/checkout@v3
        with:
          # 仓库名
          repository: opencv/opencv 
          # 项目文件名
          path: opencv-4.5.5
          # tag, branch 
          ref: 4.5.5
          submodules: recursive
    ```
    参考：[actions/checkout@v3](https://github.com/actions/checkout)
2. 压缩文件
   ```
   - name: 7zip
        run: |
          mv opencv-4.5.5/build-Release/install linux
          7z a opencv-4.6.0-ubuntu1804.7z linux
   ```

3. 上传文件
   ```
    - name: upload
    uses: actions/upload-artifact@v3
    with:
        name: opencv-4.6.0-ubuntu1804
        path: opencv-4.6.0-ubuntu1804.7z
   ```

# 参考
1. 
2. [actions/upload-artifact@v3](https://github.com/actions/upload-artifact)