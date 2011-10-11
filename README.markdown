# Torty Player

Torty is an HTML 5 audio player that falls back to Flowplayer's flash player. Here's how you use it:

# Usage

1. Include jQuery and tortyPlayer.js
2. Add your HTML 5 audio tag:
    <audio id="torty-player" preload controls src="http://www.archive.org/download/Cocaine/Cocaine.mp3"></audio>
3. Add CSS for your audio player, and the flash fallback, which will have the same id as your audio tag, but appended with "-flash"
    #torty-player, #torty-player-flash { width: 500px; height: 30px; }
4. Add some detection javascript:
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