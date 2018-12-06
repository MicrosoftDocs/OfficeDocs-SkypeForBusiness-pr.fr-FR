---
title: Messagerie instantanée et présence dans Lync Server 2013
TOCTitle: Messagerie instantanée et présence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg417162(v=OCS.15)
ms:contentKeyID: 49297511
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Messagerie instantanée et présence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-07_

Les fonctionnalités de messagerie instantanée et de présence sont automatiquement installées dans tout déploiement de Lync Server.

Les informations de *présence* permettent aux utilisateurs de contacter leurs collègues au bon moment et avec le bon mode de communication, et d’augmenter ainsi la productivité au sein de leur environnement de travail. La présence d’un utilisateur est un ensemble d’informations qui incluent la disponibilité, la volonté de communiquer, des remarques supplémentaires (comme le lieu et le statut), ainsi que la façon dont l’utilisateur peut être contacté. La fonctionnalité de présence a été améliorée dans Lync Server avec des images, des informations de lieu et un ensemble complet d’états de présence dont « Absent(e) du bureau », « Ne pas déranger » et « De retour dans quelques minutes », en plus des états de base tels que « Disponible », « Occupé(e) » et « En conférence ». Les administrateurs peuvent aussi définir des états de présence personnalisés et spécifiques à l’organisation.

Les options de gestion des contacts et d’accès utilisateur permettent aux utilisateurs de contrôler les informations que les autres personnes peuvent consulter. Les utilisateurs peuvent définir différents niveaux de contacts, chacun d’eux pouvant afficher différents niveaux d’informations de présence.

En effectuant simplement une recherche dans une liste des contacts, les utilisateurs peuvent trouver immédiatement tout ce dont ils ont besoin. Les icônes de couleur simples indiquent le statut de présence des autres utilisateurs, et l’image et le lieu sont également affichés.

Grâce à l’intégration entre Lync Server et d’autres produits tels que Outlook et SharePoint, lorsque le nom d’un contact s’affiche, comme dans un message électronique ou sur un site web d’équipe, les informations de statut et de contact sont également affichées. En outre, si vous déployez Exchange 2013, Lync Server et Exchange 2013 peuvent partager un magasin de contacts unifié qui est accessible aux clients de chaque produit.

Avec la messagerie instantanée de Lync Server, les utilisateurs peuvent s’envoyer rapidement des messages comportant des informations actuelles. Si vous le souhaitez, vos utilisateurs peuvent aussi communiquer avec les utilisateurs des réseaux de messagerie instantanée publics, tels que MSN/Windows Live, Yahoo\! et AOL. Veuillez noter qu’une licence distincte peut être requise pour la connectivité de la messagerie instantanée publique avec Windows Live, AOL et Yahoo\! Lync Server est également compatible avec le protocole XMPP (Extensible Messaging and Presence Protocol), ce qui permet à vos utilisateurs d’échanger des messages instantanés et des informations de présence avec les utilisateurs de services XMPP tels que Google Talk.

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


L’historique des conversations permet aux utilisateurs de conserver les anciennes conversations de messagerie instantanée et de récupérer des informations qui ont pu être transmises par messagerie instantanée plusieurs mois auparavant.

La conversation permanente permet aux utilisateurs de participer à des conversations de groupe, par sujet et permanentes. Les messages publiés dans les salles de conversation (forums de discussion) peuvent être permanents afin que les personnes qui se trouvent dans des sites et départements différents puissent participer, même lorsqu’elles ne sont pas toutes en ligne en même temps.

Si votre organisation doit respecter des réglementations en matière de conformité, vous pouvez déployer une fonctionnalité d’archivage des messages afin d’archiver le contenu des messages instantanés pour tous les utilisateurs de votre organisation ou seulement pour certains utilisateurs que vous spécifiez. Si vous déployez également Exchange 2013, votre archive de messagerie instantanée peut être intégrée avec la fonctionnalité d’archive permanente d’Exchange pour fournir une expérience d’administration unique pour votre conformité.

