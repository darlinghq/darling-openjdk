project(openjdk)

set(DYLIB_COMPAT_VERSION "1.0.0")
set(DYLIB_CURRENT_VERSION "1.0.0")

include_directories(
	"${CMAKE_CURRENT_SOURCE_DIR}/src/java.base/share/native/include"
	"${CMAKE_CURRENT_SOURCE_DIR}/src/java.base/unix/native/include"
	"${CMAKE_CURRENT_SOURCE_DIR}/apple/JavaNativeFoundation"
)

add_framework(JavaNativeFoundation
	FAT
	CURRENT_VERSION
	PARENT "JavaVM"
	PARENT_COMPONENT cli_gui_common
	VERSION "A"

	SOURCES
		apple/JavaNativeFoundation/JavaNativeFoundation/debug.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFAssert.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFAutoreleasePool.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFException.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFJNI.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFNumber.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFObject.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFPath.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFString.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFTypeCoercion.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFThread.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFJObjectWrapper.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFRunLoop.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFRunnable.m
		apple/JavaNativeFoundation/JavaNativeFoundation/JNFDate.m

	DEPENDENCIES
		system
		objc
		AppKit
		Foundation
)

