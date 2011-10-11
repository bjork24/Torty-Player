# Torty Player

Torty is an HTML 5 audio player that falls back to Flowplayer's flash player. Here's how you use it:

# Usage

Include jQuery and tortyPlayer.js and add your HTML 5 audio tag:

    <audio id="torty-player" preload controls src="http://www.archive.org/download/Cocaine/Cocaine.mp3"></audio>
    
Add CSS for your audio player, and the flash fallback, which will have the same id as your audio tag, but appended with "-flash"

    #torty-player, #torty-player-flash { width: 500px; height: 30px; }

Add some detection javascript:

    if($('audio').length) {
        //   
    }
    
Add some audio tag detection javascript:

    var audioTag = document.createElement('audio');
    if (!(!!(audioTag.canPlayType) && ("no" != audioTag.canPlayType("audio/mpeg")) && ("" != audioTag.canPlayType("audio/mpeg")))) {
        //
    }
    
Tell Torty Player which element to transform into the flash player

    tortyPlayer($('#torty-player'),{
        //
    });
    
Specify location for the three flowplayer elements:

    swfPlayer : 'flowplayer-3.2.7.swf',
    swfControl : 'flowplayer.controls-3.2.5.swf',
    swfAudio : 'flowplayer.audio-3.2.2.swf'
    
Once it's put together, it should look something like this:

    if($('audio').length) {
        var audioTag = document.createElement('audio');
        if (!(!!(audioTag.canPlayType) && ("no" != audioTag.canPlayType("audio/mpeg")) && ("" != audioTag.canPlayType("audio/mpeg")))) {
            tortyPlayer($('#torty-player'),{
                swfPlayer : 'flowplayer-3.2.7.swf',
                swfControl : 'flowplayer.controls-3.2.5.swf',
                swfAudio : 'flowplayer.audio-3.2.2.swf'
            });
        }    
    }
    
Enjoy the Torty!