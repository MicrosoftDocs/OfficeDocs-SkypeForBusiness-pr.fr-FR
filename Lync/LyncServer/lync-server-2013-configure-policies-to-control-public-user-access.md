---
title: 'Lync Server 2013 : configuration des stratégies de contrôle d’accès des utilisateurs publics'
description: 'Lync Server 2013 : configurez les stratégies de contrôle d’accès des utilisateurs publics.'
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
ms.openlocfilehash: 8d44437cc288d1515784af8c635f4b28902c4fa1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548730"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La connectivité PIC (Public IM Connectivity) permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée fournis par des fournisseurs de services de messagerie instantanée publics, notamment le réseau Windows Live des services Internet, Yahoo \! et AOL. Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs publics peuvent collaborer avec des utilisateurs internes de Lync Server. La connectivité de messagerie instantanée publique est une fonctionnalité ajoutée qui s’appuie sur la configuration de votre déploiement et de vos utilisateurs. Elle dépend également de la mise en service du service au niveau du fournisseur de messagerie instantanée publique. Pour plus d’informations sur la façon de configurer votre déploiement pour utiliser les fournisseurs publics, voir le Guide de mise en service de la connectivité PIC (Public IM Connectivity pour Microsoft Lync Server, Office Communications Server et Live Communications Server) : [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

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

Pour accéder au site de mise en service de la connectivité PIC de Microsoft Lync Server, utilisez le lien suivant : [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, du site et des utilisateurs. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, reportez-vous à la rubrique Configuration de la [prise en charge de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) dans la documentation de déploiement ou dans la documentation de planification. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Dans le cas des invitations de messagerie instantanée, la réponse dépend du logiciel client. La demande est acceptée, sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (c’est-à-dire les paramètres figurant dans les listes **Autoriser** et **Bloquer**). De plus, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés des utilisateurs qui ne figurent pas dans sa liste **Autoriser**.

<div>


> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs publics, même si vous n’avez pas activé la fédération pour votre organisation. Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations. En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie. Pour plus d’informations sur la spécification des utilisateurs publics pouvant se connecter à Lync Server, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync server 2013</A> dans la documentation de déploiement ou dans la documentation des opérations.



</div>

Effectuez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou plusieurs fournisseurs de messagerie instantanée publics.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Pour configurer une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs publics

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs publics, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui autorise les communications des utilisateurs publics).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs publics pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs publics**.
    
      - Pour désactiver l’accès des utilisateurs publics pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs publics**.

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs publics, vous devez aussi activer la prise en charge de la fédération dans votre organisation. Pour plus d’informations, consultez la rubrique [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs publics que vous souhaitez autoriser à collaborer avec les utilisateurs publics. Pour plus d’informations, reportez-vous à la rubrique [affectation de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

