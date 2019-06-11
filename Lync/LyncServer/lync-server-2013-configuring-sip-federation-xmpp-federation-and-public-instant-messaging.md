---
title: Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

La Fédération, la connectivité de messagerie instantanée publique et le protocole XMPP (extensible Messaging and Presence Protocol) définissent une catégorie différente d’utilisateurs externes – utilisateurs fédérés. Les utilisateurs d’un déploiement de déploiement de Lync Server ou de déploiement XMPP peuvent avoir accès à un ensemble de services limité et être authentifiés par le déploiement externe. Les utilisateurs distants sont membres de votre déploiement Lync Server et ont accès à tous les services proposés par votre déploiement.

<div>


> [!NOTE]
> Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.



</div>

La connectivité de messagerie instantanée publique est un type spécial de Fédération qui permet à un client du serveur Lync d’accéder aux fournisseurs de messagerie instantanée publics à l’aide de la 2013 Lync. Les partenaires de connectivité de messagerie instantanée publics actuels sont les suivants:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo!\!

Une configuration de connectivité de messagerie instantanée publique permet aux utilisateurs de Lync d’accéder aux utilisateurs de la connectivité de messagerie instantanée publique de la façon suivante:

  - Messagerie instantanée et présence

  - Visibilité des contacts sur la connectivité de messagerie instantanée publique dans le client Lync

  - Personne à personne conversations par messagerie instantanée avec les contacts

  - Appels audio et vidéo avec les utilisateurs de Windows Live

Lync Server Federation définit un accord entre le déploiement de votre serveur Lync et d’autres déploiements Office Communications Server 2007 R2 ou Lync Server. Une configuration fédérée de Lync Server permet aux utilisateurs de Lync d’accéder aux utilisateurs fédérés en procédant comme suit:

  - Messagerie instantanée et présence

  - Création de contacts fédérés dans le client Lync

La Fédération XMPP définit un déploiement externe en fonction du protocole de messagerie eXtensible et de présence. Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP autorisés en procédant comme suit:

  - Messagerie instantanée et présence-personne à personne uniquement

  - Créer des contacts fédérés de XMPP dans le client Lync

<div>


> [!IMPORTANT]
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Processus de déploiement de la Fédération externe du serveur Edge, de la connectivité de messagerie instantanée publique et du processus de déploiement des utilisateurs XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Autorisations</th>
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Déterminez les options à ajouter au déploiement Edge existant.</p></td>
<td><p>Exécutez le générateur de topologie pour modifier les paramètres du serveur de bord et créez et publiez la topologie. Votre topologie de périphérie existante réplique les modifications du magasin central de gestion sur le serveur Edge.</p></td>
<td><p>Groupe administrateurs de domaine et groupe RTCUniversalServerAdmins</p>



> [!NOTE]
> Vous pouvez modifier une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveurs Edge et directeurs dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Préparer l’installation</p></td>
<td><ol>
<li><p>Vérifiez que les conditions système préalables sont remplies.</p></li>
<li><p>Configurer les enregistrements DNS internes et externes pour la prise en charge de la connectivité de messagerie instantanée publique, de la Fédération Lync et de la Fédération de XMPP</p></li>
<li><p>Configurer les ports et les protocoles dans le pare-feu pour prendre en charge les types de Fédération que vous déployez</p></li>
<li><p>Obtenez et installez des certificats publics. Le temps requis pour obtenir des certificats dépend de l’autorité de certification qui émet le certificat. Cette étape est facultative à ce stade du déploiement. Si vous n’effectuez pas cette étape à ce stade, vous devez le faire pendant la configuration du serveur de périmètre. Le service Edge Server ne peut pas être démarré tant qu’aucun certificat n’est obtenu</p></li>
</ol></td>
<td><p>En fonction de votre organisation, car ces rôles sont généralement répartis entre de nombreux groupes de tâches.</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planification de la Fédération SIP, de XMPP et de la messagerie instantanée publique dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer des serveurs de périphérie pour des scénarios de Fédération</p></td>
<td><ol>
<li><p>Transférez le fichier de configuration topologique exporté vers chaque serveur Edge ou attendez la fin de la réplication.</p></li>
<li><p>Exécutez de nouveau l’Assistant déploiement pour installer les composants de prise en charge de la Fédération</p></li>
<li><p>Configurer les serveurs de périphérie</p></li>
<li><p>Demander et installer des certificats pour chaque serveur Edge</p></li>
<li><p>Redémarrer les services Edge Server</p></li>
</ol></td>
<td><p>Groupe administrateurs</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuration de la fédération Lync dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuration de la connectivité PIC dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuration de la fédération XMPP dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer la prise en charge de l’accès des utilisateurs externes.</p></td>
<td><ol>
<li><p>Utiliser l’accès aux utilisateurs externes de Lync Server Control Panel</p></li>
<li><p>Configurer une stratégie d’accès externe pour activer les communications avec les utilisateurs fédérés ou les utilisateurs publics</p></li>
<li><p>Configurer des domaines fédérés SIP pour autoriser ou bloquer des domaines</p></li>
<li><p>Activer les fournisseurs fédérés SIP pour les fournisseurs de connectivité de messagerie instantanée publics</p></li>
<li><p>Configurer des partenaires fédérés de XMPP par domaine XMPP</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins groupe ou compte d’utilisateur affecté au rôle CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configuration du chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier la configuration de votre serveur de périphérie</p></td>
<td><p>Vérifier la connectivité du serveur et la réplication des données de configuration de serveurs internes</p></td>
<td><p>Pour la vérification de la réplication, du groupe RTCUniversalServerAdmins ou du compte d’utilisateur qui est attribué à CSAdministrator roleFor vérification de la connectivité utilisateur, un utilisateur pour chaque type d’utilisateur fédéré</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérification de votre déploiement Edge dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

