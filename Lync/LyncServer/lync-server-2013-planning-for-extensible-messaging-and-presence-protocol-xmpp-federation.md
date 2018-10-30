---
title: "Plan. de féd. XMPP (Extensible Messaging and Presence Protocol) dans LS 2013"
TOCtitle: "Plan. de féd. XMPP (Extensible Messaging and Presence Protocol) dans LS 2013"
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205107(v=OCS.15)
ms:contentKeyID: 49298113
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la fédération XMPP (Extensible Messaging and Presence Protocol) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-22_

Les versions précédentes de Lync Server et Office Communications Server fournissaient une passerelle XMPP qui pouvait être déployée sur un rôle serveur séparé afin de permettre la fédération avec les déploiements XMPP. Dans Microsoft Lync Server 2013, XMPP peut être déployé comme une fonctionnalité. La fonctionnalité XMPP est installée en deux parties : un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.

Le déploiement et la configuration de XMPP sont décrits dans [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Pour prendre en charge XMPP au sein de votre organisation, vous devez prévoir la définition des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout d’enregistrements DNS. Les rubriques suivantes de cette section résument les informations nécessaires pour prévoir la fédération XMPP pour votre déploiement.

> [!IMPORTANT]  
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tiers pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

## Dans cette section

  - [Résumé des certificats - Fédération XMPP (Extensible Messaging and Presence Protocol)](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Résumé des ports - Fédération XMPP (Extensible Messaging and Presence Protocol)](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Résumé des enregistrements DNS - Fédération XMPP (Extensible Messaging and Presence Protocol)](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

## Voir aussi

#### Tâches

[Configuration de la fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  

#### Autres ressources

[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsXmppAllowedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppAllowedPartner)  
[Get-CsXmppGatewayConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppGatewayConfiguration)

