
WIN_BIN			=	$(WINDOWS_ROOT)/bin

GRAPHICS			=	$(WINDOWS_ROOT)/ts/data/graphics

IMAGE_BIN		=	$(WINDOWS_ROOT)/ts/data/graphics/image
IMAGE_DATA		=	$(WINDOWS_ROOT)/ts/data/src/image_data

do-build : $(IMAGE_DATA)/*.cpp

$(IMAGE_DATA)/*.cpp $(IMAGE_DATA)/*.h : \
./image/*.png ./uvd/*.uvd
#	$(WIN_BIN)/bg_union_dxlib -d ./bmp_sub_bg -ob $(IMAGE_BIN) -oi $(IMAGE_DATA) -f sub
	$(WIN_BIN)/uvd_union_dxlib_110805 -d $(GRAPHICS)/uvd -ob $(IMAGE_BIN) -oi $(IMAGE_DATA) -f main_3d -m
	$(WIN_BIN)/layout_union_directx -d $(GRAPHICS)/lay -o $(IMAGE_DATA) -f main_3d -m
	$(GRAPHICS)/UvdSpliter.bat
	
clean:
	rm -f ./../src/image_data/*.cpp ./../src/image_data/*.h #./split_main/*.bmp ./split_sub/*.bmp

