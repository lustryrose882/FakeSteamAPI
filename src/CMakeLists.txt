
###################################################
#                                                 #
#                                                 #
#                                                 #
#                                                 #
#                                                 #
###################################################

set ( STEAM_API_NAME steam_api )

set( CMAKE_CXX_STANDARD 17 )
set( DCMAKE_WINDOWS_EXPORT_ALL_SYMBOLS=TRUE )

set (STEAM_API_SOURCES

	./include/ISteamAppList.h
	./include/ISteamApps.h
	./include/ISteamAppTicket.h
	./include/ISteamClient.h
	./include/ISteamController.h
	./include/ISteamFriends.h
	./include/ISteamGameCoordinator.h
	./include/ISteamGameServer.h
	./include/ISteamGameServerStats.h
	./include/ISteamHTMLSurface.h
	./include/ISteamHTTP.h
	./include/ISteamInventory.h
#	./include/ISteamMasterServerUpdater.h
	./include/ISteamMusic.h
	./include/ISteamMusicRemote.h
	./include/ISteamNetworking.h
	./include/ISteamParentalSettings.h
	./include/ISteamPS3OverlayRenderHost.h
	./include/ISteamRemoteStorage.h
	./include/ISteamScreenshots.h
	./include/ISteamUGC.h
	./include/ISteamUser.h
	./include/ISteamUserStats.h
	./include/ISteamUtils.h
	./include/ISteamVideo.h

	./include/matchmakingtypes.h
	./include/steam_api_flat.h
	./include/steam_api_internal.h
	./include/steam_api.h
	./include/steam_gameserver.h
	./include/steamclientpublic.h
	./include/steamencryptedappticket.h
	./include/steamhttpenums.h
	./include/steamps3params.h
	./include/steamtypes.h
	./include/steamuniverse.h

	./FakeSteamAPI_ContextProvider.cpp
	./FakeSteamAPI_ContextProvider.h
	./FakeSteamAPI_Core.cpp
	./FakeSteamAPI_LogSys.cpp
	./FakeSteamAPI_LogSys.h
	./FakeSteamAPI_Settings.cpp
	./FakeSteamAPI_Settings.h
	./FakeSteamAPI_Utilities.cpp
	./FakeSteamAPI_Utilities.h
)

include_directories(
	./
	./include/
)

add_definitions( -DSTEAM_API_EXPORTS )

add_library ( ${STEAM_API_NAME} SHARED ${STEAM_API_SOURCES})

target_link_libraries ( ${STEAM_API_NAME}  comctl32 user32 gdi32 )

###################################################