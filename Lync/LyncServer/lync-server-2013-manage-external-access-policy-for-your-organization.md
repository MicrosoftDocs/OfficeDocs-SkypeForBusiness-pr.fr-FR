---
title: 'Lync Server 2013 : Gestion de la stratégie d’accès externe pour l’organisation'
TOCTitle: Gestion de la stratégie d’accès externe pour l’organisation
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520995(v=OCS.15)
ms:contentKeyID: 49297288
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de la stratégie d’accès externe dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-07_

Une fois que vous avez déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externes qui seront pris en charge pour votre organisation.

Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge. Les étendues de stratégies suivantes sont disponibles à des fins de création et de configuration. Par défaut, la stratégie globale est créée mais elle ne peut pas être supprimée.

  - **Stratégie globale**   La stratégie globale est créée lors du déploiement des serveurs Edge. Par défaut, aucune option d’accès des utilisateurs externes n’est activée dans cette stratégie. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous devez configurer la stratégie globale pour qu’elle prenne en charge un ou plusieurs types d’option d’accès des utilisateurs externes. La stratégie globale s’applique à tous les utilisateurs de votre organisation. Cependant, les stratégies de niveau site et utilisateur la supplantent. Si vous supprimez la stratégie globale, il n’est pas nécessaire de la retirer. Il suffit de rétablir ses paramètres par défaut.

  - **Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La stratégie de site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site. Vous pouvez affecter une stratégie utilisateur qui supplante la stratégie de site.

  - **Stratégie utilisateur**   Vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.

> [!IMPORTANT]  
> Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Ces options comprennent les types d’accès externes suivants :

  - **Autoriser les communications avec des utilisateurs fédérés**    Activez cette option si vous voulez assurer la prise en charge de l’accès des utilisateurs aux domaines partenaires fédérés. Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés tels que Microsoft Office 365. Si vous choisissez ce paramètre, vous pouvez sélectionner l’option autorisant les communications avec les domaines fédérés XMPP.
    
    Éventuellement, vous pouvez sélectionner **Autoriser les communications avec des partenaires fédérés XMPP** si vous sélectionnez au préalable **Autoriser les communications avec des utilisateurs fédérés** . La fédération XMPP est une fédération avec les organisations qui utilisent le protocole XMPP (Extensible Messaging And Presence Protocol).
    
    > [!NOTE]  
    > Si vous activez la fédération XMPP, vous devez également choisir de déployer la <strong>fédération XMPP</strong> dans la section de configuration des pools de serveurs Edge du Générateur de topologie. La configuration de la fédération XMPP déploie un proxy XMPP sur le serveur Edge et une passerelle XMPP sur le serveur frontal.

  - **Autoriser les communications avec des utilisateurs distants**    Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, par exemple, les télétravailleurs et les travailleurs itinérants, puissent se connecter à Lync Server via Internet.

  - **Autoriser les communications avec des utilisateurs publics**    Activez cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec les contacts du fournisseur de services de messagerie instantanée publics, tels que ceux proposés par Windows Live, Yahoo\! et America Online (AOL).
    
    > [!IMPORTANT]  
    > <ul>    
    > <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>    
    > <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>    
    > <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>
    > </ul>


> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous devez aussi configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs externes dans votre organisation avant que tout type d’accès des utilisateurs externes soit mis à la disposition des utilisateurs. Pour plus d’informations sur la création, la configuration et l’application des stratégies d’accès des utilisateurs externes, reportez-vous à <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a>.

**Pour afficher les stratégies d’accès externes à l’aide d’applets de commande Windows PowerShell**

  - Vous pouvez afficher les stratégies d’accès externe à l’aide de Lync Server Management Shell et de l’applet de commande **Get-CsExternalAccessPolicy**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Pour afficher des informations sur l’ensemble de vos stratégies d’accès externes, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsExternalAccessPolicy
    
    Cette commande retourn le type d’information suivant :
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

## Dans cette section

  - [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Réinitialisation ou suppression des stratégies d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

