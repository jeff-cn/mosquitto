include ../../config.mk

.PHONY: all check clean test ptest seqtest
.NOTPARALLEL:

all :

check : test

clean :
	-rm -f *.vglog *.db
	$(MAKE) -C c clean

test-compile :
	$(MAKE) -C c

ptest : test-compile msg_sequence_test
	./test.py

test : test-compile msg_sequence_test 01 02 03 04 05 06 07 08 09 10 11 12 13 14

msg_sequence_test:
	./msg_sequence_test.py

01 :
	./01-bad-initial-packets.py
	./01-connect-575314.py
	./01-connect-allow-anonymous.py
	./01-connect-disconnect-v5.py
	./01-connect-max-connections.py
	./01-connect-max-keepalive.py
	./01-connect-take-over.py
	./01-connect-uname-no-password-denied.py
	./01-connect-uname-or-anon.py
	./01-connect-uname-password-denied-no-will.py
	./01-connect-uname-password-denied.py
	./01-connect-windows-line-endings.py
	./01-connect-zero-length-id.py


02 :
	./02-shared-qos0-v5.py
	./02-subhier-crash.py
	./02-subpub-qos0-long-topic.py
	./02-subpub-qos0-oversize-payload.py
	./02-subpub-qos0-queued-bytes.py
	./02-subpub-qos0-retain-as-publish.py
	./02-subpub-qos0-send-retain.py
	./02-subpub-qos0-subscription-id.py
	./02-subpub-qos0-topic-alias-unknown.py
	./02-subpub-qos0-topic-alias.py
	./02-subpub-qos1-message-expiry-retain.py
	./02-subpub-qos1-message-expiry-will.py
	./02-subpub-qos1-message-expiry.py
	./02-subpub-qos1-nolocal.py
	./02-subpub-qos1-oversize-payload.py
	./02-subpub-qos1.py
	./02-subpub-qos2-1322.py
	./02-subpub-qos2-max-inflight-bytes.py
	./02-subpub-qos2-pubrec-error.py
	./02-subpub-qos2-receive-maximum-1.py
	./02-subpub-qos2-receive-maximum-2.py
	./02-subpub-qos2.py
	./02-subpub-recover-subscriptions.py
	./02-subscribe-dollar-v5.py
	./02-subscribe-invalid-utf8.py
	./02-subscribe-long-topic.py
	./02-subscribe-persistence-flipflop.py

03 :
	#./03-publish-qos1-queued-bytes.py
	./03-pattern-matching.py
	./03-publish-b2c-disconnect-qos1.py
	./03-publish-b2c-disconnect-qos2.py
	./03-publish-b2c-qos1-len.py
	./03-publish-b2c-qos2-len.py
	./03-publish-c2b-disconnect-qos2.py
	./03-publish-c2b-qos2-len.py
	./03-publish-dollar-v5.py
	./03-publish-dollar.py
	./03-publish-invalid-utf8.py
	./03-publish-long-topic.py
	./03-publish-qos1-max-inflight-expire.py
	./03-publish-qos1-no-subscribers-v5.py
	./03-publish-qos1-retain-disabled.py
	./03-publish-qos1.py
	./03-publish-qos2-dup.py
	./03-publish-qos2-max-inflight.py
	./03-publish-qos2.py

04 :
	./04-retain-check-source-persist-diff-port.py
	./04-retain-check-source-persist.py
	./04-retain-check-source.py
	./04-retain-clear-multiple.py
	./04-retain-qos0-clear.py
	./04-retain-qos0-fresh.py
	./04-retain-qos0-repeated.py
	./04-retain-qos0.py
	./04-retain-qos1-qos0.py
	./04-retain-upgrade-outgoing-qos.py

05 :
	./05-clean-session-qos1.py
	./05-session-expiry-v5.py

06 :
	./06-bridge-b2br-disconnect-qos1.py
	./06-bridge-b2br-disconnect-qos2.py
	./06-bridge-b2br-late-connection-retain.py
	./06-bridge-b2br-late-connection.py
	./06-bridge-b2br-remapping.py
	./06-bridge-br2b-disconnect-qos1.py
	./06-bridge-br2b-disconnect-qos2.py
	./06-bridge-br2b-remapping.py
	./06-bridge-clean-session-csF-lcsF.py
	./06-bridge-clean-session-csF-lcsN.py
	./06-bridge-clean-session-csF-lcsT.py
	./06-bridge-clean-session-csT-lcsF.py
	./06-bridge-clean-session-csT-lcsN.py
	./06-bridge-clean-session-csT-lcsT.py
	./06-bridge-fail-persist-resend-qos1.py
	./06-bridge-fail-persist-resend-qos2.py
	./06-bridge-no-local.py
	./06-bridge-outgoing-retain.py
	./06-bridge-per-listener-settings.py
	./06-bridge-reconnect-local-out.py
	./06-bridge-remap-receive-wildcard.py

07 :
	./07-will-control.py
	./07-will-delay-invalid-573191.py
	./07-will-delay-reconnect.py
	./07-will-delay-recover.py
	./07-will-delay-session-expiry.py
	./07-will-delay-session-expiry2.py
	./07-will-delay.py
	./07-will-disconnect-with-will.py
	./07-will-invalid-utf8.py
	./07-will-no-flag.py
	./07-will-null-topic.py
	./07-will-null.py
	./07-will-oversize-payload.py
	./07-will-per-listener.py
	./07-will-properties.py
	./07-will-qos0.py
	./07-will-reconnect-1273.py
	./07-will-takeover.py

08 :
ifeq ($(WITH_TLS),yes)
	./08-ssl-bridge.py
	./08-ssl-connect-cert-auth-crl.py
	./08-ssl-connect-cert-auth-expired.py
	./08-ssl-connect-cert-auth-revoked.py
	./08-ssl-connect-cert-auth-without.py
	./08-ssl-connect-cert-auth.py
	./08-ssl-connect-identity.py
	./08-ssl-connect-no-auth-wrong-ca.py
	./08-ssl-connect-no-auth.py
	./08-ssl-connect-no-identity.py
	./08-ssl-hup-disconnect.py
ifeq ($(WITH_TLS_PSK),yes)
	./08-tls-psk-pub.py
	./08-tls-psk-bridge.py
endif
endif

09 :
	./09-acl-access-variants.py
	./09-acl-change.py
	./09-acl-empty-file.py
	./09-auth-bad-method.py
	./09-extended-auth-change-username.py
	./09-extended-auth-multistep-reauth.py
	./09-extended-auth-multistep.py
	./09-extended-auth-reauth.py
	./09-extended-auth-single.py
	./09-plugin-acl-change.py
	./09-plugin-auth-acl-pub.py
	./09-plugin-auth-acl-sub-denied.py
	./09-plugin-auth-acl-sub.py
	./09-plugin-auth-context-params.py
	./09-plugin-auth-defer-unpwd-fail.py
	./09-plugin-auth-defer-unpwd-success.py
	./09-plugin-auth-msg-params.py
	./09-plugin-auth-unpwd-fail.py
	./09-plugin-auth-unpwd-success.py
	./09-plugin-auth-v2-unpwd-fail.py
	./09-plugin-auth-v2-unpwd-success.py
	./09-plugin-publish.py
	./09-plugin-tick.py
	./09-pwfile-parse-invalid.py

10 :
	./10-listener-mount-point.py

11 :
	./11-message-expiry.py
	./11-persistent-subscription.py
	./11-persistent-subscription-v5.py
	./11-persistent-subscription-no-local.py
	./11-pub-props.py
	./11-subscription-id.py

12 :
	./12-prop-assigned-client-identifier.py
	./12-prop-maximum-packet-size-broker.py
	./12-prop-maximum-packet-size-publish-qos1.py
	./12-prop-maximum-packet-size-publish-qos2.py
	./12-prop-response-topic-correlation-data.py
	./12-prop-response-topic.py
	./12-prop-server-keepalive.py
	./12-prop-subpub-content-type.py
	./12-prop-subpub-payload-format.py

13 :
	./13-malformed-publish-v5.py
	./13-malformed-subscribe-v5.py
	./13-malformed-unsubscribe-v5.py

14 :
ifeq ($(WITH_TLS),yes)
ifeq ($(WITH_CJSON),yes)
	./14-dynsec-acl.py
	./14-dynsec-anon-group.py
	./14-dynsec-auth.py
	./14-dynsec-client.py
	./14-dynsec-client-invalid.py
	./14-dynsec-default-access.py
	./14-dynsec-disable-client.py
	./14-dynsec-group.py
	./14-dynsec-group-invalid.py
	./14-dynsec-modify-client.py
	./14-dynsec-modify-group.py
	./14-dynsec-modify-role.py
	./14-dynsec-plugin-invalid.py
	./14-dynsec-role.py
	./14-dynsec-role-invalid.py
endif
endif
