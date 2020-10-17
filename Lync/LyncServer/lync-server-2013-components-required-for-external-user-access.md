---
title: 'Lync Server 2013 : composants requis pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a97635c66d66703fc2e9879024004a95c2c09eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502451"
---
# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Composants requis pour l’accès des utilisateurs externes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-29_

La plupart des composants Edge sont déployés dans un réseau de périmètre. Les deux composants suivants forment la topologie de périphérie du réseau de périmètre. Sauf indication contraire, les composants font partie des [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) et se trouvent dans le réseau de périmètre. Ces composants de périphérie sont les suivants :

  - Serveurs de périphérie

  - Proxys inverses

  - Pare-feu

  - Directeurs (facultatifs et logiquement situés sur le réseau interne)

  - Équilibrage de la charge pour les topologies Edge mises à l’échelle (avec charge DNS équilibrée ou un programme d’équilibrage de la charge matérielle)
    
    <div>
    

    > [!IMPORTANT]  
    > L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS.

    
    </div>

<div>

## <a name="edge-servers"></a>Serveurs de périphérie

Les serveurs Edge envoient et reçoivent le trafic réseau pour les services offerts par les utilisateurs externes par le déploiement interne. Il exécute les services suivants :

  - Service Edge d' **accès**     Le service Edge d’accès fournit un point de connexion approuvé unique pour le trafic SIP (Session Initiation Protocol) entrant et sortant.

  - Service Edge de **conférence Web**     Le service Edge de conférence Web permet aux utilisateurs externes de participer à des réunions hébergées sur votre déploiement interne de Lync Server 2013.

  - Service Edge A **/V**     Le service Edge A/V rend l’audio, la vidéo, le partage d’application et le transfert de fichiers accessibles aux utilisateurs externes. Vos utilisateurs peuvent ajouter de l’audio et de la vidéo à des réunions qui incluent des participants externes et ils peuvent communiquer à l’aide de l’audio et/ou de la vidéo directement avec un utilisateur externe dans les sessions de point à point. Le service Edge A/V fournit également une prise en charge pour le partage du Bureau et le transfert de fichiers.

  - **Service**     proxy XMPP Le service proxy XMPP accepte et envoie les messages XMPP (extensible Messaging and Presence Protocol) vers et depuis les partenaires fédérés XMPP configurés.

Les utilisateurs externes autorisés peuvent accéder aux serveurs Edge afin de se connecter à votre déploiement interne de Lync Server 2013, mais les serveurs Edge ne permettent pas d’autres accès au réseau interne.

<div>


> [!NOTE]  
> Les serveurs Edge sont déployés pour fournir des connexions pour les clients Lync activés et d’autres serveurs Microsoft Edge (comme dans les scénarios de Fédération). Ils ne sont pas conçus pour autoriser les connexions d’autres types de client d’extrémité ou de serveur. Le serveur de passerelle XMPP peut être déployé pour autoriser les connexions avec les partenaires XMPP configurés. Le serveur Edge et la passerelle XMPP peuvent uniquement prendre en charge les connexions d’extrémité à partir de ces types de client et de fédération.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy inverse

Le proxy inverse est requis pour les actions suivantes :

  - permettre aux utilisateurs de participer à des réunions ou à des conférences à distance via des URL simples ;

  - permettre aux utilisateurs externes de télécharger le contenu de réunions ;

  - permettre aux utilisateurs externes de développer des groupes de distribution ;

  - permettre à l’utilisateur d’obtenir un certificat utilisateur pour l’authentification basée sur un certificat client ;

  - permettre aux utilisateurs distants de télécharger des fichiers à partir du serveur de carnet d’adresses ou soumettre des requêtes au service de requête web du carnet d’adresses ;

  - permettre aux utilisateurs distants d’obtenir des mises à jour de logiciels clients et de périphériques ;

  - permettre aux appareils mobiles de découvrir automatiquement les serveurs frontaux qui proposent des services de mobilité ;

  - Pour activer les notifications de transmission vers les appareils mobiles à partir de Microsoft 365, Office 365 ou Apple

Pour plus d’informations sur les proxys inverses et sur les exigences auxquelles doivent répondre les proxys inverses, voir les détails relatifs à la [Configuration requise pour le proxy inverse dans Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Les utilisateurs externes n’ont pas besoin d’une connexion de réseau privé virtuel (VPN) à votre organisation afin de participer aux communications à l’aide de Lync Server 2013. Si vous avez implémenté la technologie VPN dans votre organisation et que vos utilisateurs utilisent le VPN pour Lync, le trafic multimédia (par exemple, la vidéoconférence) peut être compromis. Vous devez envisager de permettre au trafic multimédia de se connecter directement au service Edge AV et de contourner le VPN. Pour plus d’informations, reportez-vous à l’article du blog NextHop, « activation de médias Lync pour contourner un tunnel VPN », à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> .



</div>

</div>

<div>

## <a name="firewall"></a>-

Vous pouvez déployer votre topologie de périmètre avec un seul pare-feu externe ou un pare-feu interne et un pare-feu externe. Les architectures de scénario incluent deux pare-feu. Il est recommandé d’utiliser deux pare-feu pour garantir le routage strict d’un côté du réseau à l’autre et protéger votre déploiement interne derrière deux niveaux de pare-feu.

</div>

<div>

## <a name="director"></a>Directeur

Un directeur est un rôle serveur distinct et facultatif dans Lync Server 2013 qui n’utilise pas de compte d’utilisateur personnel, ou fournit des services de présence ou de conférence. Il sert de serveur de tronçon suivant interne vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le pool d’accueil de l’utilisateur. En préauthentifiant le directeur, vous pouvez supprimer des demandes de comptes d’utilisateurs qui ne sont pas répertoriés dans le déploiement.

Un directeur aide à isoler les serveurs Standard Edition et les serveurs frontaux dans les pools frontaux Enterprise Edition du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé avec du trafic externe non valide lors d’une attaque de ce type, le trafic se termine au niveau du directeur. Pour plus d’informations sur l’utilisation des directeurs, reportez-vous à [la rubrique Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour le programme d’équilibrage de la charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

