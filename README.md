# staza.io-jingle
A tweaked version of stanza.io to fix a problem where call answer fails when calling audio only from firefox to chrome and throws this error: 

*Failed to set remote answer sdp: Called with SDP without ice-ufrag and ice-pwd.*

i've solved the issue by including the npm package sdpparser in the client js (of stanza.io) then building it again,
and in stanza.io.bundle.js ive tweaked the `PeerConnection.prototype.handleAnswer` to remove the media fingerprint of the video if call is audio only.
you may see this thread if you need more explanation on the issue: https://github.com/otalk/jingle.js/issues/24
