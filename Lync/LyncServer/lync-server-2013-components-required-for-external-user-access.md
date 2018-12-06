---
title: 'Lync Server 2013 : Composants requis pour l’accès des utilisateurs externes'
TOCTitle: Composants requis pour l’accès des utilisateurs externes
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425779(v=OCS.15)
ms:contentKeyID: 49296723
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants requis pour l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La plupart des composants Edge sont déployés sur un réseau de périmètre. Les composants suivants forment la topologie Edge du réseau de périmètre. Sauf indication contraire, ils sont inclus dans les [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) et se trouvent sur le réseau de périmètre. Ces composants Edge sont les suivants :

  - serveurs Edge

  - Proxys inverses

  - Pare-feu

  - directeurs (facultatif et logiquement situé sur le réseau interne)

  - Équilibrage de la charge pour les topologies Edge mises à l’échelle (avec charge DNS équilibrée ou un équilibreur de la charge matérielle)
    
    > [!IMPORTANT]  
    > L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS.

## serveurs Edge

Les serveurs Edge envoient et reçoivent du trafic réseau pour les services offerts par déploiement interne par les utilisateurs externes. Le serveur Edge exécute les services suivants :

  - **Service Edge d’accès** : le service Edge d’accès fournit un point de connexion unique sécurisé utilisé pour le trafic SIP (Session Initiation Protocol) à la fois sortant et entrant.

  - **Service Edge de conférence web** : le service Edge de conférence web permet aux utilisateurs externes de participer à des réunions organisées au sein de votre déploiement Lync Server 2013 interne.

  - **Service Edge A/V** : le service Edge A/V rend l’audio, la vidéo, le partage d’applications et le transfert de fichiers accessibles aux utilisateurs externes. Vos utilisateurs peuvent ajouter l’audio et la vidéo aux réunions qui incluent des participants externes et communiquer par audio et/ou vidéo directement avec un utilisateur externe dans des sessions point à point. Le service Edge A/V fournit également une prise en charge pour le partage du Bureau et le transfert de fichiers.

  - **Service proxy XMPP**   Le service proxy XMPP accepte et envoie les messages XMPP (Extensible Messaging and Presence Protocol) à destination et en provenance des partenaires fédérés XMPP configurés.

Les utilisateurs externes autorisés peuvent accéder aux serveurs Edge pour se connecter à votre déploiement Lync Server 2013 interne. Cependant, les serveurs Edge ne donnent aucun autre moyen d’accès au réseau interne.

> [!NOTE]  
> Les serveurs Edge sont déployés pour fournir des connexions aux clients activés et autres serveurs Edge Microsoft (comme dans les scénarios de fédération). Ils ne permettent pas d’autoriser des connexions depuis d’autres types de client ou serveur de terminaison. Le serveur de passerelle XMPP peut être déployé pour autoriser les connexions avec les partenaires XMPP configurés. Le serveur Edge et la passerelle XMPP ne peuvent prendre en charge que les connexions de terminaison de ces types de client et de fédération.

## Proxy inverse

Le proxy inverse est requis pour les actions suivantes :

  - permettre aux utilisateurs de participer à des réunions ou à des conférences à distance via des URL simples ;

  - permettre aux utilisateurs externes de télécharger le contenu de réunions ;

  - permettre aux utilisateurs externes de développer des groupes de distribution ;

  - permettre à l’utilisateur d’obtenir un certificat utilisateur pour l’authentification basée sur un certificat client ;

  - permettre aux utilisateurs distants de télécharger des fichiers à partir du serveur de carnet d’adresses ou soumettre des requêtes au service de requête sur le web du carnet d’adresses ;

  - permettre aux utilisateurs distants d’obtenir des mises à jour de logiciels clients et de périphériques ;

  - permettre aux appareils mobiles de découvrir automatiquement les serveurs frontaux qui proposent des services de mobilité ;

  - permettre d’envoyer des notifications push aux appareils mobiles depuis les services de notification push Office 365 ou Apple.

Pour plus d’informations sur les proxys inverses et sur les conditions qu’ils doivent remplir, reportez-vous à [Configuration requise pour le proxy inverse dans Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

> [!NOTE]  
> Les utilisateurs externes ne doivent pas se connecter à votre organisation via un réseau privé virtuel (VPN) pour participer à toute communication via Lync Server 2013. Si votre organisation a mis en œuvre la technologie VPN et que vos utilisateurs se servent du VPN pour le Lync, le trafic multimédia (tel que les conférences vidéo) peut en pâtir. Vous devez envisager de proposer un moyen de connecter le trafic multimédia directement au service Edge A/V et contourner le VPN. Pour plus d’informations, reportez-vous à l’article « Enabling Lync Media to Bypass a VPN Tunnel » du blog NextHop, à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</a>.

## Pare-feu

Vous pouvez déployer votre topologie Edge avec un seul pare-feu externe ou à la fois un pare-feu interne et un pare-feu externe. Les architectures du scénario incluent deux pare-feu. Il est recommandé d’utiliser deux pare-feu pour garantir le routage strict d’un côté du réseau à l’autre et protéger votre déploiement interne derrière deux niveaux de pare-feu.

## directeur

Un directeur est un rôle serveur distinct et facultatif dans Lync Server 2013 qui n’héberge pas de comptes d’utilisateur ni ne fournit de services de présence ou de conférence. Il sert de serveur du tronçon suivant interne vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie au préalable les requêtes entrantes et les redirige vers le pool ou le serveur central de l’utilisateur. L’authentification préalable au niveau du directeur vous permet d’annuler les requêtes des comptes d’utilisateur inconnus au déploiement.

Un directeur aide à isoler les serveurs Standard Edition et les serveurs principaux des pools de serveurs frontaux Enterprise Edition du trafic malveillant, tel que les attaques par déni de service. Si le réseau est inondé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur. Pour plus d’informations sur l’utilisation des directeurs, reportez-vous à [Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

## Voir aussi

#### Concepts

[Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)

