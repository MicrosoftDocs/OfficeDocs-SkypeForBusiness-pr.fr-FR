---
title: "Lync Server 2013 : Conf. des féd. SIP et XMPP et mess. inst. publique."
TOCTitle: Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205134(v=OCS.15)
ms:contentKeyID: 49298447
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La fédération, la connectivité PIC et le protocole XMPP (Extensible Messaging and Presence Protocol) définissent une classe différente d’utilisateurs externes : les utilisateurs fédérés. Les utilisateurs d’un déploiement XMPP ou d’un déploiement Lync Server fédéré ont accès à un ensemble de services limité et sont authentifiés par le déploiement externe. Les utilisateurs distants sont des membres de votre déploiement Lync Server et ont accès à tous les services offerts par votre déploiement.

> [!NOTE]  
> Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo!. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.

La connectivité PIC est un type spécial de fédération qui permet à un client Lync Server d’accéder à des partenaires de messagerie instantanée publique configurés à l’aide de Lync 2013. Les partenaires de connectivité PIC actuels sont les suivants :

  -   
    America Online

  -   
    Windows Live

  -   
    Yahoo\!

Une configuration de connectivité PIC permet aux utilisateurs de Lync d’accéder à des utilisateurs de connectivité PIC grâce à :

  - Messagerie instantanée et présence

  - Visibilité des contacts de connectivité PIC dans le client Lync

  - Conversations de messagerie instantanée de personne à personne avec des contacts

  - Appels audio et vidéo avec des utilisateurs de Windows Live

La fédération Lync Server définit un contrat entre votre déploiement de Lync Server et d’autres déploiements d’Office Communications Server 2007 R2 ou de Lync Server. Une configuration fédérée de Lync Server permet aux utilisateurs de Lync d’accéder aux utilisateurs fédérés grâce à :

  - Messagerie instantanée et présence

  - Création de contacts fédérés dans le client Lync

La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP autorisés grâce à :

  - Messagerie instantanée et présence – de personne à personne uniquement

  - Création de contacts fédérés XMPP dans le client Lync

> [!IMPORTANT]  
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tiers pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

## Fédération externe de serveur Edge, connectivité PIC et processus de déploiement d’utilisateurs XMPP


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
<td><p>Exécuter le Générateur de topologie pour modifier les paramètres du serveur Edge et créer et publier la topologie. Votre topologie Edge existante répliquera les modifications du magasin central de gestion vers le serveur Edge.</p></td>
<td><p>Groupe Administrateurs du domaine et groupe RTCUniversalServerAdmins</p>
<div>

> [!NOTE]  
> Vous pouvez modifier une topologie à l’aide d’un compte qui est membre du groupe d’utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveurs Edge et directeurs dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Préparer l’installation</p></td>
<td><ol><li><p>Assurez-vous que les conditions préalables du système sont respectées.</p></li><li><p>Configurer les enregistrements DNS internes et externes afin de prendre en charge la connectivité PIC, la fédération Lync et la fédération XMPP</p></li><li><p>Configurer les ports et protocoles au niveau du pare-feu afin de prendre en charge les types de fédération que vous déployez</p></li><li><p>Obtenir et installer les certificats publics. La durée nécessaire à l’obtention des certificats dépend de l’autorité de certification qui émet le certificat. Cette étape est facultative à ce stade du déploiement. Si vous ne l’effectuez pas maintenant, vous devez le faire durant la configuration du serveur Edge. Le service du serveur Edge ne peut pas être démarré avant l’obtention des certificats.</p></li></ol>
<p></p></td>
<td><p>En fonction de votre organisation, car ces rôles sont généralement distribués parmi plusieurs groupes de travail</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planification pour la fédération SIP, la fédération XMPP et la messagerie instantanée publique dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurer les serveurs Edge pour les scénarios de fédération</p></td>
<td><ol><li><p>Transporter le fichier de configuration de topologie exporté vers chaque serveur Edge ou laisser la réplication se terminer</p></li><li><p>Réexécuter l’Assistant Déploiement pour installer les composants de prise en charge pour la fédération</p></li><li><p>Configurer les serveurs Edge</p></li><li><p>Demander et installer des certificats pour chaque serveur Edge</p></li><li><p>Redémarrer les services du serveur Edge</p></li></ol></td>
<td><p>Groupe Administrateurs</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuration de la fédération Lync dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuration de la connectivité PIC dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuration de la fédération XMPP dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer la prise en charge de l’accès des utilisateurs externes</p></td>
<td><ol><li><p>Utiliser l’Accès des utilisateurs externes dans le Panneau de configuration Lync Server</p></li><li><p>Configurer la stratégie d’accès externe pour activer les communications avec les utilisateurs fédérés ou publics</p></li><li><p>Configurer des domaines fédérés SIP pour autoriser ou bloquer des domaines</p></li><li><p>Activer des fournisseurs fédérés SIP pour les fournisseurs de connectivité PIC</p></li><li><p>Configurer des partenaires fédérés XMPP par domaine XMPP</p></li></ol></td>
<td><p>Groupe RTCUniversalServerAdmins ou compte d’utilisateur affecté au rôle CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configuration du chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013</a></p></td>
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

