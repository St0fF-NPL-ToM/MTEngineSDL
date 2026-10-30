#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    App.h
    AsyncSocket.h
    AsyncSocketData.h
    BloomFilter.h
    CachingApp.h
    ChunkedEncoding.h
    ClientApp.h
    Http3App.h
    Http3Context.h
    Http3ContextData.h
    Http3Request.h
    Http3Response.h
    Http3ResponseData.h
    HttpContext.h
    HttpContextData.h
    HttpErrors.h
    HttpParser.h
    HttpResponse.h
    HttpResponseData.h
    HttpRouter.h
    libusockets.h
    LocalCluster.h
    Loop.h
    LoopData.h
    MessageParser.h
    MoveOnlyFunction.h
    Multipart.h
    PerMessageDeflate.h
    ProxyParser.h
    QueryParser.h
    TopicTree.h
    Utilities.h
    WebSocket.h
    WebSocketContext.h
    WebSocketContextData.h
    WebSocketData.h
    WebSocketExtensions.h
    WebSocketHandshake.h
    WebSocketProtocol.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
