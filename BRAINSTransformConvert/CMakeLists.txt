
##- project(BRAINSTransformConvert)

#-----------------------------------------------------------------------------
# Dependencies.
#

#
# ITK
#

FindITKUtil(BRAINSTransformConvert_ITK
  ITKTransform
  ITKImageCompare
  ITKThresholding
  ITKDistanceMap)

#-----------------------------------------------------------------------------
# Output directories.
#

set(MODULE_FOLDER "Module-BRAINSTransformConvert")

set(ALL_PROGS_LIST
  BRAINSTransformConvert
)

foreach(prog ${ALL_PROGS_LIST})
  StandardBRAINSBuildMacro(NAME ${prog} TARGET_LIBRARIES BRAINSCommonLib )
endforeach()

if(BUILD_TESTING AND NOT BRAINSTools_DISABLE_TESTING)
    add_subdirectory(TestSuite)
endif()
