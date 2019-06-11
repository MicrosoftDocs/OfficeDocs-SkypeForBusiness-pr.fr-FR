---
title: 'Lync Server 2013 : Gestion de la stratégie d’accès externe pour l’organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Gestion de la stratégie d’accès externe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer les types d’accès externe qui seront pris en charge pour votre organisation.

Par défaut, il n’y a pas de stratégies configurées pour prendre en charge l’accès des utilisateurs externes, y compris les accès utilisateurs distants, l’accès des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes pour votre organisation. Pour contrôler l’utilisation de l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge pour chaque stratégie. Les étendues de stratégie suivantes sont disponibles pour la création et la configuration. Par défaut, la stratégie globale est créée, mais elle ne peut pas être supprimée.

  - **Politique globale la**   stratégie globale est créée lors du déploiement de votre serveur Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous pouvez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateurs externes. La politique globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous rétablissez la valeur par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès des utilisateurs distants pour un site spécifique. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur à un utilisateur pour remplacer le paramètre de stratégie de site.

  - **Stratégie**   de l’utilisateur vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration de la stratégie utilisateur remplace la stratégie globale et la stratégie de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale et la stratégie de site, vous pouvez spécifier une stratégie d’utilisateur qui désactive l’accès des utilisateurs distants, puis affecter cette stratégie à des utilisateurs spécifiques. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle ne soit appliquée.

<div>


> [!IMPORTANT]  
> Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.



</div>

Ces options incluent les types d’accès externes suivants:

  - **Activer les communications avec les utilisateurs**   fédérés activez cette fonction si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés. Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés tels que Microsoft Office 365. Le choix de ce paramètre vous permet de sélectionner l’option permettant de communiquer avec des domaines fédérés XMPP.
    
    Vous pouvez également sélectionner l’option **activer les communications avec les partenaires fédérés de XMPP** si vous activez **d’abord activer les communications avec les utilisateurs fédérés**. La Fédération XMPP est une Fédération avec des organisations qui utilisent le protocole XMPP (extensible Messaging and Presence Protocol).
    
    <div>
    

    > [!NOTE]  
    > Si vous activez la Fédération XMPP, vous devez également choisir de déployer la <STRONG>Fédération XMPP</STRONG> dans la section Configuration de pools de périphérie du générateur de topologie. La configuration de la Fédération XMPP déploie un proxy XMPP sur le serveur Edge et une passerelle XMPP sur le serveur frontal.

    
    </div>

  - **Activer les communications avec les utilisateurs**   distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu (par exemple, les télétravailleurs et les utilisateurs qui voyagent) puissent se connecter à Lync Server via Internet.

  - **Activer les communications avec les utilisateurs**   publics activez cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec des contacts de fournisseurs de messagerie instantanée publics, tels que ceux fournis\!par Windows Live, Yahoo et America Online (AOL).
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
    > <LI>
    > <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</P>
    > <LI>
    > <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> Outre l’activation de la prise en charge de l’accès des utilisateurs externes, vous devez également configurer des stratégies pour contrôler l’utilisation de l’accès des utilisateurs externes au sein de votre organisation avant de pouvoir accéder aux utilisateurs externes. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A>.



</div>

**Pour afficher les stratégies d’accès externe à l’aide des cmdlets Windows PowerShell**

  - Vous pouvez afficher les stratégies d’accès externe à l’aide de Lync Server Management Shell et de l’applet **de passe Get-CsExternalAccessPolicy** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».
    
    Pour afficher des informations sur les stratégies d’accès externe, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsExternalAccessPolicy
    
    Cette commande renvoie le type d’informations suivant :
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Réinitialisation ou suppression des stratégies d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

