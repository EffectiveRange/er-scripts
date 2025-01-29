cmake_minimum_required(VERSION 3.22)

include(ERBuild NO_POLICY_SCOPE)


set(er-scripts-ver 1.0.1)

project(er-scripts VERSION ${er-scripts-ver} DESCRIPTION "This project contains various script utilities")

ER_DEPS()


install(FILES scripts/gstack DESTINATION  /usr/local/bin/ PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)
install(FILES scripts/logged DESTINATION  /usr/local/bin/ PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)
install(FILES scripts/record DESTINATION  /usr/local/bin/ PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)

# systemctl enable recog.service
# systemctl start recog.service
# install(FILES service/recog.service DESTINATION  /etc/systemd/system)



ER_ENABLE_TEST()


# set(CPACK_DEBIAN_PACKAGE_CONTROL_EXTRA "${CMAKE_CURRENT_SOURCE_DIR}/service/postinst;${CMAKE_CURRENT_SOURCE_DIR}/service/prerm")
ER_PACK()