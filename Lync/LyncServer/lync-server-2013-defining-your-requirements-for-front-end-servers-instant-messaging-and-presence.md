---
title: "LS 2013 : Déf. de la conf. req. pour serv. frontaux, mess. inst. et présence"
TOCTitle: Définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412956(v=OCS.15)
ms:contentKeyID: 49298734
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-07_

La principale tâche de planification pour la messagerie instantanée et la présence est de vous assurer que vous disposez de suffisamment de serveurs frontaux pour vos utilisateurs.

## Activation des communications avec les utilisateurs externes

Vous tirerez beaucoup plus profit de votre investissement dans Lync Server en permettant à vos utilisateurs de communiquer avec des utilisateurs externes. Exemples d’utilisateurs externes :

  - **Utilisateurs distants**   Utilisateurs appartenant à votre organisation, lorsqu’ils se trouvent en dehors de vos pare-feu et qu’ils utilisent un ordinateur portable ou d’autres périphériques Lync Server.

  - **Utilisateurs fédérés**   Utilisateurs appartenant aux entreprises avec lesquelles vous travaillez et qui exécutent aussi Lync Server. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises.

  - **Utilisateurs publics**   Utilisateurs de services de messagerie instantanée publics (tels que les services de messagerie instantanée fournis par le réseau de services Internet Windows Live, Yahoo\! et AOL), et utilisateurs de fournisseurs et de serveurs employant le protocole XMPP (Extensible Messaging and Presence Protocol), comme Google Talk.
    
    > [!NOTE]  
    > Veuillez noter qu’une licence distincte peut être requise pour la connectivité de la messagerie instantanée publique avec Windows Live, AOL et Yahoo! 
    
       
    > [!IMPORTANT]  
    > <ul>    
    > <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>    
    > <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>    
    > <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>
    > </ul>


Pour activer un scénario ou l’ensemble d’entre eux, vous devez déployer un serveur Edge pour davantage sécuriser les communications entre votre déploiement Lync Server et des utilisateurs externes. Les utilisateurs distants de votre organisation et les utilisateurs d’organisations fédérées seront en mesure de détecter leur présence mutuelle et de communiquer via la messagerie instantanée. Pour plus d’informations sur la mise en place de communications avec des utilisateurs externes, reportez-vous à [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.

## Archivage du contenu de la messagerie instantanée

Lync Server offre des fonctionnalités utiles si votre organisation doit respecter des réglementations en matière de conformité. Vous pouvez utiliser la fonctionnalité d’archivage pour archiver le contenu des messages instantanés soit pour tous les utilisateurs de votre organisation, soit uniquement pour ceux que vous indiquez. Pour plus d’informations, reportez-vous à [Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.

Si vous avez également déployé Microsoft Exchange Server 2013, vous pouvez intégrer l’archivage des données Exchange avec l’archivage des données Lync Server, puis utiliser le même outil pour effectuer des recherches dans ces deux types de données archivées. Pour plus d’informations, reportez-vous à [Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

