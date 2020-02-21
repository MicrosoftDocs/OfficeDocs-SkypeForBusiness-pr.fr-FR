---
title: 'Lync Server 2013 : gestion de la stratégie d’accès externe pour votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55ca35ace807c5e8e551295f3d395e85d514b901
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Gérer la stratégie d’accès externe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externe qui seront pris en charge pour votre organisation.

Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge. Les étendues de stratégies suivantes sont disponibles à des fins de création et de configuration. Par défaut, la stratégie globale est créée mais elle ne peut pas être supprimée.

  - **Stratégie globale la**   stratégie globale est créée lorsque vous déployez vos serveurs Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous configurez la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès des utilisateurs externes. La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous devez rétablir le paramètre par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur qui supplante la configuration de la stratégie de site.

  - **Stratégie utilisateur vous**   pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.

<div>


> [!IMPORTANT]  
> Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.



</div>

Ces options comprennent les types d’accès externes suivants :

  - **Activer les communications avec les utilisateurs**   fédérés activez cette fonction si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés. Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés comme Microsoft Office 365. Si vous choisissez ce paramètre, vous pouvez sélectionner l’option autorisant les communications avec les domaines fédérés XMPP.
    
    Éventuellement, vous pouvez sélectionner **Autoriser les communications avec des partenaires fédérés XMPP** si vous sélectionnez au préalable **Autoriser les communications avec des utilisateurs fédérés**. La fédération XMPP est une fédération avec les organisations qui utilisent le protocole XMPP (Extensible Messaging And Presence Protocol).
    
    <div>
    

    > [!NOTE]  
    > Si vous activez la Fédération XMPP, vous devez également choisir de déployer la <STRONG>Fédération XMPP</STRONG> dans la section Configuration des pools de serveurs Edge du générateur de topologie. La configuration de la Fédération XMPP consiste à déployer un proxy XMPP sur le serveur Edge et une passerelle XMPP sur le serveur frontal.

    
    </div>

  - **Activer les communications avec des utilisateurs**   distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, tels que les télétravailleurs et les utilisateurs itinérants, puissent se connecter à Lync Server via Internet.

  - **Activer les communications avec les utilisateurs**   publics activez cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec les contacts de fournisseur de messagerie instantanée publique, tels que ceux fournis\!par Windows Live, Yahoo et America Online (AOL).
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
    > <LI>
    > <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
    > <LI>
    > <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous devez aussi configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs externes dans votre organisation avant que tout type d’accès des utilisateurs externes ne soit mis à la disposition des utilisateurs. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A>.



</div>

**Pour afficher les stratégies d’accès externe à l’aide des applets de commande Windows PowerShell**

  - Vous pouvez afficher les stratégies d’accès externe à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsExternalAccessPolicy** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.
    
    Pour afficher des informations sur toutes vos stratégies d’accès externe, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsExternalAccessPolicy
    
    Cette commande renvoie le type d’information suivant :
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés XMPP dans Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Réinitialisation ou suppression des stratégies d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

