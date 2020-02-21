---
title: Configuration de la Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94590e669c17328a33b8af62eda46e861aec6bdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configuration de la Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La fédération, la connectivité de messagerie instantanée publique et le protocole XMPP (Extensible Messaging and Presence Protocol) définissent une classe différente d’utilisateurs externes : les utilisateurs fédérés. Les utilisateurs d’un déploiement de Lync Server fédéré ou d’un déploiement XMPP ont accès à un ensemble limité de services et sont authentifiés par le déploiement externe. Les utilisateurs distants sont membres de votre déploiement Lync Server et ont accès à tous les services offerts par votre déploiement.

<div>


> [!NOTE]
> Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.



</div>

La connectivité de messagerie instantanée publique est un type de Fédération particulier qui permet à un client Lync Server d’accéder à des partenaires de messagerie instantanée publics configurés à l’aide de Lync 2013. Les partenaires de connectivité de messagerie instantanée publique actuels sont les suivants :

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

Une configuration de connectivité de messagerie instantanée publique permet aux utilisateurs de Lync d’accéder à des utilisateurs de connectivité de messagerie instantanée publique grâce à :

  - Messagerie instantanée et présence

  - Visibilité des contacts de connectivité de messagerie instantanée publique dans le client Lync

  - Conversations de messagerie instantanée de personne à personne avec des contacts

  - Appels audio et vidéo avec des utilisateurs de Windows Live

La fédération Lync Server définit un contrat entre votre déploiement de Lync Server et d’autres déploiements d’Office Communications Server 2007 R2 ou de Lync Server. Une configuration fédérée de Lync Server permet aux utilisateurs de Lync d’accéder aux utilisateurs fédérés grâce à :

  - Messagerie instantanée et présence

  - Création de contacts fédérés dans le client Lync

La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP autorisés grâce à :

  - Messagerie instantanée et présence – de personne à personne uniquement

  - la création de contacts fédérés XMPP dans le client Lync.

<div>


> [!IMPORTANT]
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Fédération externe de serveur Edge, connectivité de messagerie instantanée publique et processus de déploiement d’utilisateurs XMPP


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
<td><p>Déterminer les options à ajouter au déploiement Edge existant</p></td>
<td><p>Exécutez le générateur de topologie pour modifier les paramètres du serveur Edge et créer et publier la topologie. Votre topologie Edge existante répliquera les modifications du magasin central de gestion sur le serveur Edge.</p></td>
<td><p>Groupe Administrateurs du domaine et groupe RTCUniversalServerAdmins</p>



> [!NOTE]
> Vous pouvez modifier une topologie à l’aide d’un compte qui est membre du groupe d’utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveur Edge et de directeur dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Préparer l’installation</p></td>
<td><ol>
<li><p>S’assurer que la configuration système requise est satisfaite.</p></li>
<li><p>Configurer les enregistrements DNS internes et externes afin de prendre en charge la connectivité de messagerie instantanée publique, la fédération Lync et la fédération XMPP</p></li>
<li><p>Configurer les ports et protocoles au niveau du pare-feu afin de prendre en charge les types de fédération que vous déployez</p></li>
<li><p>Obtenir et installer les certificats publics. La durée nécessaire à l’obtention des certificats dépend de l’autorité de certification qui émet le certificat. Cette étape est facultative à ce stade du déploiement. Si vous ne l’effectuez pas maintenant, vous devez le faire durant la configuration du serveur Edge. Le service du serveur Edge ne peut pas être démarré avant l’obtention des certificats.</p></li>
</ol></td>
<td><p>En fonction de votre organisation, car ces rôles sont généralement distribués parmi plusieurs groupes de travail</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer les serveurs Edge pour les scénarios de fédération</p></td>
<td><ol>
<li><p>Transporter le fichier de configuration de topologie exporté vers chaque serveur Edge ou laisser la réplication se terminer</p></li>
<li><p>Réexécuter l’Assistant Déploiement pour installer les composants de prise en charge pour la fédération</p></li>
<li><p>Configurer les serveurs Edge</p></li>
<li><p>Demander et installer des certificats pour chaque serveur Edge</p></li>
<li><p>Redémarrer les services du serveur Edge</p></li>
</ol></td>
<td><p>Groupe Administrateurs</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuration de la Fédération Lync dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuration de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuration de la Fédération XMPP dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer la prise en charge de l’accès des utilisateurs externes</p></td>
<td><ol>
<li><p>Utilisation de l’accès des utilisateurs externes au panneau de configuration Lync Server</p></li>
<li><p>Configurer la stratégie d’accès externe pour activer les communications avec les utilisateurs fédérés ou publics</p></li>
<li><p>Configurer des domaines fédérés SIP pour autoriser ou bloquer des domaines</p></li>
<li><p>Activer des fournisseurs fédérés SIP pour les fournisseurs de connectivité de messagerie instantanée publique</p></li>
<li><p>Configurer des partenaires fédérés XMPP par domaine XMPP</p></li>
</ol></td>
<td><p>Groupe RTCUniversalServerAdmins ou compte d’utilisateur affecté au rôle CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurer le chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier votre configuration de serveur Edge</p></td>
<td><p>Vérifier la connectivité serveur et la réplication des données de configuration à partir des serveurs internes</p></td>
<td><p>Pour la vérification de la réplication, un groupe RTCUniversalServerAdmins ou compte d’utilisateur affecté au rôle CSAdministrator. Pour la vérification de la connectivité utilisateur, un utilisateur de chaque type d’utilisateur fédéré</p></td>
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

