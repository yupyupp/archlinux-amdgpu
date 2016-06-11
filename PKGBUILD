# Maintainer: Janusz Lewandowski <lew21@xtreeme.org>
# Autogenerated from AMD's Packages file

pkgver_base=16.20.3
pkgver_build=294842

pkgbase=amdgpu-pro-installer
pkgname=(amdgpu-pro amdgpu-pro-clinfo amdgpu-pro-computing amdgpu-pro-core amdgpu-pro-dkms amdgpu-pro-graphics lib32-amdgpu-pro-lib32 lib32-amdgpu-pro-libopencl-dev amdgpu-pro-libopencl-dev lib32-amdgpu-pro-libopencl1 amdgpu-pro-libopencl1 lib32-amdgpu-pro-opencl-icd amdgpu-pro-opencl-icd amdgpu-pro-vulkan-driver lib32-amdgpu-pro-vulkan-driver libdrm-amdgpu-pro-amdgpu1 lib32-libdrm-amdgpu-pro-amdgpu1 lib32-libdrm-amdgpu-pro-dev libdrm-amdgpu-pro-dev libdrm-amdgpu-pro-tools libdrm2-amdgpu-pro lib32-libdrm2-amdgpu-pro libegl1-amdgpu-pro lib32-libegl1-amdgpu-pro libegl1-amdgpu-pro-dev lib32-libegl1-amdgpu-pro-dev lib32-libgbm-amdgpu-pro-dev libgbm-amdgpu-pro-dev lib32-libgbm1-amdgpu-pro libgbm1-amdgpu-pro libgl1-amdgpu-pro-dev lib32-libgl1-amdgpu-pro-dev libgl1-amdgpu-pro-dri lib32-libgl1-amdgpu-pro-dri lib32-libgl1-amdgpu-pro-glx libgl1-amdgpu-pro-glx libgles2-amdgpu-pro lib32-libgles2-amdgpu-pro libgles2-amdgpu-pro-dev lib32-libgles2-amdgpu-pro-dev libvdpau-amdgpu-pro lib32-libvdpau-amdgpu-pro xserver-xorg-video-amdgpu-pro)
pkgver=${pkgver_base}.${pkgver_build}
pkgrel=1
arch=('x86_64')
url="http://www.amd.com"
license=('custom:AMD')

url_ref="http://support.amd.com/en-us/kb-articles/Pages/AMDGPU-PRO-Beta-Driver-for-Vulkan-Release-Notes.aspx"
DLAGENTS="https::/usr/bin/curl --referer ${url_ref} -o %o %u"

source=(https://www2.ati.com/drivers/beta/amdgpu-pro_${pkgver_base}-${pkgver_build}.tar.xz)
sha256sums=('4a2988f5047e858c3c6ae22528162b2537780deeaf5dda5d8a8f61e213058a66')


package_amdgpu-pro () {
	pkgdesc="This package install all amdgpu-pro components."
	depends=('amdgpu-pro-graphics' 'amdgpu-pro-computing')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_amdgpu-pro-clinfo () {
	pkgdesc="AMD OpenCL info utility"
	depends=('amdgpu-pro-libopencl1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-clinfo_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-clinfo_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-clinfo_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-clinfo_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_amdgpu-pro-computing () {
	pkgdesc="This package install amdgpu-pro OpenCL components."
	depends=('amdgpu-pro-core' 'amdgpu-pro-clinfo' 'amdgpu-pro-opencl-icd' 'amdgpu-pro-libopencl-dev')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-computing_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-computing_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-computing_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-computing_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_amdgpu-pro-core () {
	pkgdesc="This package switchs the GPU stack to amdgpu-pro with basic components."
	depends=('linux-firmware' 'libdrm-amdgpu-pro-amdgpu1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-core_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-core_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-core_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-core_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz

	mv ${pkgdir}/lib ${pkgdir}/usr/
	mkdir -p ${pkgdir}/etc/ld.so.conf.d/
	ln -s /usr/lib/amdgpu-pro/ld.conf ${pkgdir}/etc/ld.so.conf.d/10-amdgpu-pro.conf
	mkdir -p ${pkgdir}/etc/modprobe.d/
	ln -s /usr/lib/amdgpu-pro/modprobe.conf ${pkgdir}/etc/modprobe.d/amdgpu-pro.conf
	install=amdgpu-pro-core.install

}


package_amdgpu-pro-dkms () {
	pkgdesc="amdgpu-pro driver in DKMS format."
	depends=('dkms>=1.95')
	arch=('any')

	rm -Rf "${srcdir}"/amdgpu-pro-dkms_16.20.3-294842_all
	mkdir "${srcdir}"/amdgpu-pro-dkms_16.20.3-294842_all
	cd "${srcdir}"/amdgpu-pro-dkms_16.20.3-294842_all
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-dkms_16.20.3-294842_all.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_amdgpu-pro-graphics () {
	pkgdesc="This package install amdgpu-pro graphics components."
	depends=('amdgpu-pro-core' 'libgles2-amdgpu-pro' 'libgl1-amdgpu-pro-dev' 'libgl1-amdgpu-pro-dri' 'xserver-xorg-video-amdgpu-pro' 'amdgpu-pro-vulkan-driver' 'libvdpau-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-graphics_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-graphics_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-graphics_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-graphics_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-amdgpu-pro-lib32 () {
	pkgdesc="This package contains x86 libs for x86_64 machine usage."
	depends=('lib32-libgles2-amdgpu-pro' 'lib32-libgl1-amdgpu-pro-dev' 'lib32-libgl1-amdgpu-pro-dri' 'lib32-libgbm1-amdgpu-pro' 'lib32-amdgpu-pro-opencl-icd' 'lib32-amdgpu-pro-libopencl-dev' 'lib32-amdgpu-pro-vulkan-driver' 'lib32-libvdpau-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-lib32_16.20.3-294842_i386
	mkdir "${srcdir}"/amdgpu-pro-lib32_16.20.3-294842_i386
	cd "${srcdir}"/amdgpu-pro-lib32_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-lib32_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_lib32-amdgpu-pro-libopencl-dev () {
	pkgdesc="AMD OpenCL ICD Loader library"
	depends=('lib32-amdgpu-pro-libopencl1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-libopencl-dev_16.20.3-294842_i386
	mkdir "${srcdir}"/amdgpu-pro-libopencl-dev_16.20.3-294842_i386
	cd "${srcdir}"/amdgpu-pro-libopencl-dev_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-libopencl-dev_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_amdgpu-pro-libopencl-dev () {
	pkgdesc="AMD OpenCL ICD Loader library"
	depends=('amdgpu-pro-libopencl1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-libopencl-dev_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-libopencl-dev_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-libopencl-dev_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-libopencl-dev_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-amdgpu-pro-libopencl1 () {
	pkgdesc="AMD OpenCL ICD Loader library"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-libopencl1_16.20.3-294842_i386
	mkdir "${srcdir}"/amdgpu-pro-libopencl1_16.20.3-294842_i386
	cd "${srcdir}"/amdgpu-pro-libopencl1_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-libopencl1_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_amdgpu-pro-libopencl1 () {
	pkgdesc="AMD OpenCL ICD Loader library"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-libopencl1_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-libopencl1_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-libopencl1_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-libopencl1_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-amdgpu-pro-opencl-icd () {
	pkgdesc="non-free AMD OpenCL ICD Loaders"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-opencl-icd_16.20.3-294842_i386
	mkdir "${srcdir}"/amdgpu-pro-opencl-icd_16.20.3-294842_i386
	cd "${srcdir}"/amdgpu-pro-opencl-icd_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-opencl-icd_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_amdgpu-pro-opencl-icd () {
	pkgdesc="non-free AMD OpenCL ICD Loaders"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-opencl-icd_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-opencl-icd_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-opencl-icd_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-opencl-icd_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_amdgpu-pro-vulkan-driver () {
	pkgdesc="AMDGPU Pro Vulkan driver"
	depends=('libdrm-amdgpu-pro-amdgpu1' 'libx11' 'libxcb' 'libxcb>=1.9.2' 'libxext' 'libxshmfence')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-vulkan-driver_16.20.3-294842_amd64
	mkdir "${srcdir}"/amdgpu-pro-vulkan-driver_16.20.3-294842_amd64
	cd "${srcdir}"/amdgpu-pro-vulkan-driver_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-vulkan-driver_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-amdgpu-pro-vulkan-driver () {
	pkgdesc="AMDGPU Pro Vulkan driver"
	depends=('lib32-libdrm-amdgpu-pro-amdgpu1' 'lib32-libx11' 'lib32-libxcb' 'lib32-libxcb>=1.9.2' 'lib32-libxext' 'lib32-libxshmfence')
	arch=('x86_64')

	rm -Rf "${srcdir}"/amdgpu-pro-vulkan-driver_16.20.3-294842_i386
	mkdir "${srcdir}"/amdgpu-pro-vulkan-driver_16.20.3-294842_i386
	cd "${srcdir}"/amdgpu-pro-vulkan-driver_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./amdgpu-pro-vulkan-driver_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libdrm-amdgpu-pro-amdgpu1 () {
	pkgdesc="Userspace interface to amdgpu-specific kernel DRM services -- runtime"
	depends=('libdrm2-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_amd64
	mkdir "${srcdir}"/libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_amd64
	cd "${srcdir}"/libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libdrm-amdgpu-pro-amdgpu1 () {
	pkgdesc="Userspace interface to amdgpu-specific kernel DRM services -- runtime"
	depends=('lib32-libdrm2-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_i386
	mkdir "${srcdir}"/libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_i386
	cd "${srcdir}"/libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm-amdgpu-pro-amdgpu1_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_lib32-libdrm-amdgpu-pro-dev () {
	pkgdesc="Userspace interface to kernel DRM services -- development files"
	depends=('lib32-libdrm2-amdgpu-pro' 'lib32-libdrm-amdgpu-pro-amdgpu1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm-amdgpu-pro-dev_16.20.3-294842_i386
	mkdir "${srcdir}"/libdrm-amdgpu-pro-dev_16.20.3-294842_i386
	cd "${srcdir}"/libdrm-amdgpu-pro-dev_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm-amdgpu-pro-dev_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libdrm-amdgpu-pro-dev () {
	pkgdesc="Userspace interface to kernel DRM services -- development files"
	depends=('libdrm2-amdgpu-pro' 'libdrm-amdgpu-pro-amdgpu1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm-amdgpu-pro-dev_16.20.3-294842_amd64
	mkdir "${srcdir}"/libdrm-amdgpu-pro-dev_16.20.3-294842_amd64
	cd "${srcdir}"/libdrm-amdgpu-pro-dev_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm-amdgpu-pro-dev_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_libdrm-amdgpu-pro-tools () {
	pkgdesc="testing tools for libdrm-amdgpu-pro"
	depends=('libdrm-amdgpu-pro-amdgpu1' 'libdrm2-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm-amdgpu-pro-tools_16.20.3-294842_amd64
	mkdir "${srcdir}"/libdrm-amdgpu-pro-tools_16.20.3-294842_amd64
	cd "${srcdir}"/libdrm-amdgpu-pro-tools_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm-amdgpu-pro-tools_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_libdrm2-amdgpu-pro () {
	pkgdesc="Userspace interface to kernel DRM services -- runtime"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm2-amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/libdrm2-amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/libdrm2-amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm2-amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libdrm2-amdgpu-pro () {
	pkgdesc="Userspace interface to kernel DRM services -- runtime"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/libdrm2-amdgpu-pro_16.20.3-294842_i386
	mkdir "${srcdir}"/libdrm2-amdgpu-pro_16.20.3-294842_i386
	cd "${srcdir}"/libdrm2-amdgpu-pro_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libdrm2-amdgpu-pro_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libegl1-amdgpu-pro () {
	pkgdesc="implementation of the EGL API -- runtime"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/libegl1-amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/libegl1-amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/libegl1-amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libegl1-amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libegl1-amdgpu-pro () {
	pkgdesc="implementation of the EGL API -- runtime"
	depends=()
	arch=('x86_64')

	rm -Rf "${srcdir}"/libegl1-amdgpu-pro_16.20.3-294842_i386
	mkdir "${srcdir}"/libegl1-amdgpu-pro_16.20.3-294842_i386
	cd "${srcdir}"/libegl1-amdgpu-pro_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libegl1-amdgpu-pro_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libegl1-amdgpu-pro-dev () {
	pkgdesc="implementation of the EGL API -- development files"
	depends=('libegl1-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libegl1-amdgpu-pro-dev_16.20.3-294842_amd64
	mkdir "${srcdir}"/libegl1-amdgpu-pro-dev_16.20.3-294842_amd64
	cd "${srcdir}"/libegl1-amdgpu-pro-dev_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libegl1-amdgpu-pro-dev_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libegl1-amdgpu-pro-dev () {
	pkgdesc="implementation of the EGL API -- development files"
	depends=('lib32-libegl1-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libegl1-amdgpu-pro-dev_16.20.3-294842_i386
	mkdir "${srcdir}"/libegl1-amdgpu-pro-dev_16.20.3-294842_i386
	cd "${srcdir}"/libegl1-amdgpu-pro-dev_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libegl1-amdgpu-pro-dev_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_lib32-libgbm-amdgpu-pro-dev () {
	pkgdesc="generic buffer management API -- development files"
	depends=('lib32-libgbm1-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgbm-amdgpu-pro-dev_16.20.3-294842_i386
	mkdir "${srcdir}"/libgbm-amdgpu-pro-dev_16.20.3-294842_i386
	cd "${srcdir}"/libgbm-amdgpu-pro-dev_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgbm-amdgpu-pro-dev_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libgbm-amdgpu-pro-dev () {
	pkgdesc="generic buffer management API -- development files"
	depends=('libgbm1-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgbm-amdgpu-pro-dev_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgbm-amdgpu-pro-dev_16.20.3-294842_amd64
	cd "${srcdir}"/libgbm-amdgpu-pro-dev_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgbm-amdgpu-pro-dev_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libgbm1-amdgpu-pro () {
	pkgdesc="generic buffer management API -- runtime"
	depends=('lib32-libdrm-amdgpu-pro-amdgpu1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgbm1-amdgpu-pro_16.20.3-294842_i386
	mkdir "${srcdir}"/libgbm1-amdgpu-pro_16.20.3-294842_i386
	cd "${srcdir}"/libgbm1-amdgpu-pro_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgbm1-amdgpu-pro_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libgbm1-amdgpu-pro () {
	pkgdesc="generic buffer management API -- runtime"
	depends=('libdrm-amdgpu-pro-amdgpu1')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgbm1-amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgbm1-amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/libgbm1-amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgbm1-amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_libgl1-amdgpu-pro-dev () {
	pkgdesc="implementation of the OpenGL API -- GLX development files"
	depends=('libgl1-amdgpu-pro-glx')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgl1-amdgpu-pro-dev_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgl1-amdgpu-pro-dev_16.20.3-294842_amd64
	cd "${srcdir}"/libgl1-amdgpu-pro-dev_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgl1-amdgpu-pro-dev_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libgl1-amdgpu-pro-dev () {
	pkgdesc="implementation of the OpenGL API -- GLX development files"
	depends=('lib32-libgl1-amdgpu-pro-glx')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgl1-amdgpu-pro-dev_16.20.3-294842_i386
	mkdir "${srcdir}"/libgl1-amdgpu-pro-dev_16.20.3-294842_i386
	cd "${srcdir}"/libgl1-amdgpu-pro-dev_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgl1-amdgpu-pro-dev_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libgl1-amdgpu-pro-dri () {
	pkgdesc="implementation of the OpenGL API -- DRI modules"
	depends=('libx11' 'libxext')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgl1-amdgpu-pro-dri_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgl1-amdgpu-pro-dri_16.20.3-294842_amd64
	cd "${srcdir}"/libgl1-amdgpu-pro-dri_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgl1-amdgpu-pro-dri_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libgl1-amdgpu-pro-dri () {
	pkgdesc="implementation of the OpenGL API -- DRI modules"
	depends=('lib32-libx11' 'lib32-libxext')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgl1-amdgpu-pro-dri_16.20.3-294842_i386
	mkdir "${srcdir}"/libgl1-amdgpu-pro-dri_16.20.3-294842_i386
	cd "${srcdir}"/libgl1-amdgpu-pro-dri_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgl1-amdgpu-pro-dri_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_lib32-libgl1-amdgpu-pro-glx () {
	pkgdesc="implementation of the OpenGL API -- GLX runtime"
	depends=('lib32-libdrm2-amdgpu-pro' 'lib32-libx11>=1.4.99.1' 'lib32-libxcb>=1.8' 'lib32-libxcb' 'lib32-libxdamage>=1.1' 'lib32-libxext' 'lib32-libxfixes' 'lib32-libxxf86vm')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgl1-amdgpu-pro-glx_16.20.3-294842_i386
	mkdir "${srcdir}"/libgl1-amdgpu-pro-glx_16.20.3-294842_i386
	cd "${srcdir}"/libgl1-amdgpu-pro-glx_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgl1-amdgpu-pro-glx_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libgl1-amdgpu-pro-glx () {
	pkgdesc="implementation of the OpenGL API -- GLX runtime"
	depends=('libdrm2-amdgpu-pro' 'libx11>=1.4.99.1' 'libxcb>=1.8' 'libxcb' 'libxdamage>=1.1' 'libxext' 'libxfixes' 'libxxf86vm')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgl1-amdgpu-pro-glx_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgl1-amdgpu-pro-glx_16.20.3-294842_amd64
	cd "${srcdir}"/libgl1-amdgpu-pro-glx_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgl1-amdgpu-pro-glx_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_libgles2-amdgpu-pro () {
	pkgdesc="implementation of the OpenGL|ES 2.x API -- runtime"
	depends=('libegl1-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgles2-amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgles2-amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/libgles2-amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgles2-amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libgles2-amdgpu-pro () {
	pkgdesc="implementation of the OpenGL|ES 2.x API -- runtime"
	depends=('lib32-libegl1-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgles2-amdgpu-pro_16.20.3-294842_i386
	mkdir "${srcdir}"/libgles2-amdgpu-pro_16.20.3-294842_i386
	cd "${srcdir}"/libgles2-amdgpu-pro_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgles2-amdgpu-pro_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libgles2-amdgpu-pro-dev () {
	pkgdesc="implementation of the OpenGL|ES 2.x API -- development files"
	depends=('libgles2-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgles2-amdgpu-pro-dev_16.20.3-294842_amd64
	mkdir "${srcdir}"/libgles2-amdgpu-pro-dev_16.20.3-294842_amd64
	cd "${srcdir}"/libgles2-amdgpu-pro-dev_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libgles2-amdgpu-pro-dev_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libgles2-amdgpu-pro-dev () {
	pkgdesc="implementation of the OpenGL|ES 2.x API -- development files"
	depends=('lib32-libgles2-amdgpu-pro')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libgles2-amdgpu-pro-dev_16.20.3-294842_i386
	mkdir "${srcdir}"/libgles2-amdgpu-pro-dev_16.20.3-294842_i386
	cd "${srcdir}"/libgles2-amdgpu-pro-dev_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libgles2-amdgpu-pro-dev_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_libvdpau-amdgpu-pro () {
	pkgdesc="AMDGPU Pro VDPAU driver"
	depends=('libdrm-amdgpu-pro-amdgpu1' 'libdrm>=2.4.31' 'libdrm2-amdgpu-pro' 'openssl>=1.0.0' 'libx11' 'libxcb>=1.8' 'libxcb')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libvdpau-amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/libvdpau-amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/libvdpau-amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./libvdpau-amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
}


package_lib32-libvdpau-amdgpu-pro () {
	pkgdesc="AMDGPU Pro VDPAU driver"
	depends=('lib32-libdrm-amdgpu-pro-amdgpu1' 'lib32-libdrm>=2.4.31' 'lib32-libdrm2-amdgpu-pro' 'lib32-openssl>=1.0.0' 'lib32-libx11' 'lib32-libxcb>=1.8' 'lib32-libxcb' 'lib32-zlib>=1.2.0')
	arch=('x86_64')

	rm -Rf "${srcdir}"/libvdpau-amdgpu-pro_16.20.3-294842_i386
	mkdir "${srcdir}"/libvdpau-amdgpu-pro_16.20.3-294842_i386
	cd "${srcdir}"/libvdpau-amdgpu-pro_16.20.3-294842_i386
	ar x "${srcdir}"/amdgpu-pro-driver/./libvdpau-amdgpu-pro_16.20.3-294842_i386.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	rm -Rf ${pkgdir}/usr/share/doc ${pkgdir}/usr/include
}


package_xserver-xorg-video-amdgpu-pro () {
	pkgdesc="X.Org X server -- AMD/ATI Amdgpu-Pro display driver"
	depends=('libdrm-amdgpu-pro-amdgpu1' 'libdrm2-amdgpu-pro' 'libepoxy>=1.0' 'libgbm1-amdgpu-pro' 'libgl1-amdgpu-pro-glx' 'libsystemd>=183' 'libx11' 'libxcb' 'libxdamage>=1.1' 'libxext' 'libxfixes' 'libxxf86vm' 'xorg-server')
	arch=('x86_64')

	rm -Rf "${srcdir}"/xserver-xorg-video-amdgpu-pro_16.20.3-294842_amd64
	mkdir "${srcdir}"/xserver-xorg-video-amdgpu-pro_16.20.3-294842_amd64
	cd "${srcdir}"/xserver-xorg-video-amdgpu-pro_16.20.3-294842_amd64
	ar x "${srcdir}"/amdgpu-pro-driver/./xserver-xorg-video-amdgpu-pro_16.20.3-294842_amd64.deb
	tar -C "${pkgdir}" -xf data.tar.xz
	ln -sfn 1.18 ${pkgdir}/usr/lib/x86_64-linux-gnu/amdgpu-pro/xorg
}
