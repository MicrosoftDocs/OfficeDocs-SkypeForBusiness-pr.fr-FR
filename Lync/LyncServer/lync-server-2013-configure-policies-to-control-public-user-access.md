---
title: 'Lync Server 2013 : Configuration des stratégies de contrôle d’accès des utilisateurs publics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs de services de messagerie instantanée publics, y\!compris le réseau Windows Live de services Internet, Yahoo et AOL. Pour contrôler si les utilisateurs publics peuvent collaborer avec des utilisateurs externes du serveur Lync, vous devez configurer une ou plusieurs stratégies d’accès aux utilisateurs externes. La connectivité de messagerie instantanée publique est une fonctionnalité ajoutée qui repose sur la configuration de votre déploiement et de vos utilisateurs. Ce service dépend également de la configuration du service auprès du fournisseur de messagerie instantanée publique. Pour plus d’informations sur la façon de configurer votre déploiement pour utiliser les fournisseurs publics, voir le Guide de mise en service de la connectivité PIC (Public IM Connectivity pour Microsoft Lync Server, Office Communications Server et Live Communications Server» :[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>



</div>

Pour accéder au site de mise en service de Microsoft Lync Server Public IM Connectivity, utilisez le lien suivant :[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, au niveau du site et de l’utilisateur. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir Configuration de la [prise en charge de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) dans la documentation de déploiement ou la documentation de planification. Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de serveur Lync est défini comme suit : la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.

Dans le cas d’invitations de messagerie instantanée, la réponse dépend du logiciel client. La requête est acceptée sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (autrement dit, les paramètres du client de l’utilisateur **autorisent** et **bloquent** les listes). Par ailleurs, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés de tous les utilisateurs qui ne figurent pas dans sa liste **verte** .

<div>


> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs publics, même si vous n’avez pas activé la Fédération pour votre organisation. Toutefois, les stratégies que vous configurez ne s’appliquent que lorsque la Fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations. Par ailleurs, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie. Pour plus d’informations sur la spécification des utilisateurs publics qui peuvent se connecter à Lync Server, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès utilisateur externe à un utilisateur compatible Lync dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.



</div>

Utilisez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou de plusieurs fournisseurs de messagerie instantanée publics.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Pour configurer une stratégie d’accès externe pour prendre en charge l’accès public aux utilisateurs

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale de manière à prendre en charge l’accès public aux utilisateurs, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**. Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnablePublicUsers** pour une stratégie utilisateur qui autorise les communications pour les utilisateurs publics).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès public aux utilisateurs de la stratégie, activez la case à cocher **activer les communications avec les utilisateurs publics** .
    
      - Pour désactiver l’accès public aux utilisateurs de la stratégie, décochez la case **activer les communications avec les utilisateurs publics** .

7.  Cliquez sur **Valider**.

Pour activer l’accès public aux utilisateurs, vous devez également activer la prise en charge de la Fédération au sein de votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs publics que vous souhaitez pouvoir collaborer avec des utilisateurs publics. Pour plus d’informations, reportez-vous à la section [attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

