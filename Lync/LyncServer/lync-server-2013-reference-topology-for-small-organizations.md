---
title: Topologie de référence de Lync Server 2013 pour les petites organisations
TOCTitle: Topologie de référence pour les petites organisations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398095(v=OCS.15)
ms:contentKeyID: 49296106
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologie de référence de Lync Server 2013 pour les petites organisations

 

_**Dernière rubrique modifiée :** 2013-10-07_

La topologie de référence pour les petites organisations vous montre comment déployer une solution fiable, hautement disponible en déployant uniquement trois serveurs exécutant Lync Server.

**Topologie de référence pour les petites organisations**

![Diagramme de topologie de référence déployant trois serveurs](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagramme de topologie de référence déployant trois serveurs")

  - **Paire de serveurs Standard Edition déployés**     Le site central de cette organisation regroupe 4 000 utilisateurs. Deux serveurs Standard Edition ont été déployés et appariés pour obtenir une meilleure disponibilité et assurer une récupération d’urgence optimale. Chaque serveur héberge 2 000 utilisateurs, mais les informations concernant tous les utilisateurs sont synchronisées entre les deux serveurs. Si l’un des serveurs ne fonctionne pas, un administrateur peut faire basculer les utilisateurs sur l’autre serveur, avec une perturbation minime. Pour plus d’informations sur les fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013, reportez-vous à [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Le déploiement d’un serveur Edge est recommandé.**    Même si n’est pas nécessaire de déployer un serveur Edge pour la messagerie instantanée interne ainsi que pour les fonctionnalités de présence et de conférence, nous recommandons de le faire même pour des petits déploiements. Vous pouvez optimiser votre investissement dans Lync Server en déployant un serveur Edge pour fournir des services aux utilisateurs se trouvant hors des pare-feu de votre organisation. Les avantages sont les suivants :
    
      - Les utilisateurs de votre organisation peuvent utiliser les fonctionnalités de Lync Server, s’ils travaillent de chez eux ou s’ils sont en déplacement.
    
      - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
      - Si un partenaire, un fournisseur ou un client avec qui vous êtes en relation, utilise également Lync Server, vous pouvez former une *relation fédérée* avec l’organisation de cette personne. Le déploiement Lync Server reconnaîtra alors les utilisateurs de cette organisation fédérée pour une meilleure collaboration.
    
      - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics, notamment : Windows Live, AOL, Yahoo\! et Google Talk. Une licence distincte peut être nécessaire pour la connectivité de la messagerie instantanée publique avec ces services.
        
        > [!IMPORTANT]  
        > <ul>        
        > <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>        
        > <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>        
        > <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>
        > </ul>


  - **Survivabilité du site de succursale.** Cette organisation exécute un programme pilote de la fonction Voix Entreprise de Lync Server. Certains utilisateurs utilisent Lync Server comme solution vocale unique. Certains de ces utilisateurs du pilote de Voix Entreprise sont situés sur le site de la succursale. Le site de la succursale ne dispose pas d’une liaison de réseau étendu (WAN) fiable vers le site central, par conséquent un Survivable Branch Appliance y est déployé. Ainsi, si la liaison de réseau étendu ne fonctionne pas, les utilisateurs sur le site de la succursale peuvent continuer à passer et à recevoir des appels (au sein de l’organisation et des appels RTC), à utiliser leur messagerie vocale et à communiquer par le biais de la messagerie instantanée à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison de réseau étendu n’est plus disponible.

  - **Déploiement de la messagerie unifiée Exchange**    Cette topologie de référence inclut un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server et non Lync Server
    
    Pour plus d’informations sur la messagerie unifiée Exchange, reportez-vous à [Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [Intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Serveur Office Web Apps Server.** Nous recommandons de déployer un serveur Office Web Apps Server ou une batterie de serveurs Office Web Apps Server dans chaque organisation qui utilise les conférences web. Office Web Apps Server permet de présenter des diapositives PowerPoint dans les conférences web. Pour plus d’informations, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

