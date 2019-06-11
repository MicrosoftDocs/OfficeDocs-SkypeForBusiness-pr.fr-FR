---
title: 'Lync Server 2013 : Activation ou désactivation de la fédération et de la connectivité PIC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-06-24_

La prise en charge de la Fédération est requise pour permettre aux utilisateurs disposant d’un compte auprès d’un client ou d’une organisation de partenaire approuvés, notamment des domaines de partenariat et des utilisateurs de fournisseurs de messagerie instantanée publics que vous prenez en charge, pour collaborer avec des utilisateurs dans votre société. La Fédération est également requise pour l’utilisation d’un fournisseur de services Exchange hébergés pour fournir des messages vocaux aux utilisateurs vocaux d’entreprise dont la boîte aux lettres est située sur un service Exchange hébergé tel que Microsoft Exchange Online. Lorsque vous établissez une relation d’approbation avec ces domaines externes, vous pouvez autoriser des utilisateurs dans ces domaines à accéder à votre déploiement et participer aux communications de Lync Server. Cette relation d’approbation est appelée Fédération et ne dépend pas d’une relation d’approbation Active Directory ou n’est pas liée.

Pour prendre en charge l’accès par des utilisateurs de domaines fédérés, vous devez activer la Fédération. Si vous activez la Fédération pour votre organisation, vous devez également spécifier si vous voulez implémenter les options suivantes:

  - **Activer la découverte**   de domaine partenaire si vous activez cette option, Lync Server utilise des enregistrements DNS (Domain Name System) pour essayer de détecter les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de la découverte fédérée partenaires et limiter ou bloquer ce trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs des domaines que vous incluez dans la liste des domaines autorisés. Si vous sélectionnez cette option, vous pouvez spécifier que les domaines individuels doivent être bloqués ou autorisés, y compris limiter l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations sur le contrôle d’accès par des domaines fédérés, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Envoyer une exclusion de responsabilité à l’archivage pour les partenaires**     fédérés vous recevez des notifications de non-responsabilité pour les partenaires fédérés dans lesquels l’archivage de votre déploiement est en place. Si vous prise en charge de l’archivage des communications externes avec les domaines de partenaires fédérés, vous devez activer la notification d’exclusion de responsabilité de l’archivage pour avertir les partenaires de l’archivage de leurs messages.

Si vous souhaitez par la suite empêcher l’accès temporaire ou définitive aux utilisateurs de domaines fédérés, vous pouvez désactiver la Fédération pour votre organisation. Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés pour votre organisation, y compris les options de Fédération appropriées qui doivent être prises en charge pour votre organisation.

<div>


> [!NOTE]  
> L’activation de la Fédération pour votre organisation indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés. Les utilisateurs dans les domaines fédérés ne peuvent pas participer à la messagerie instantanée ou aux conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés. Les utilisateurs des fournisseurs de service de messagerie instantanée publique ne peuvent pas participer à la messagerie instantanée ou aux conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie pour la prise en charge de la connectivité PIC. Lync Server ne peut pas utiliser un service Exchange hébergé pour fournir des réponses aux appels, Outlook Voice Access (y compris la messagerie vocale), ou les services de standard automatique pour les utilisateurs dont la boîte aux lettres est située sur un service Exchange hébergé tant que vous n’avez pas configuré une stratégie de messagerie vocale hébergée. qui fournit des informations de routage. Pour plus d’informations sur la configuration des stratégies de communication avec des utilisateurs de domaines fédérés dans d’autres organisations, voir <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</A> dans la documentation opérations. Par ailleurs, si vous souhaitez prendre en charge les communications avec les utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies pour le prendre en charge et configurer également la prise en charge des fournisseurs de services individuels que vous voulez prendre en charge. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gérer les fournisseurs fédérés SIP pour votre organisation dans</A> la documentation des opérations de Lync Server 2013. Pour plus d’informations sur la création d’une stratégie de messagerie vocale hébergée, consultez <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">gérer les stratégies de messagerie vocale hébergées dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis cliquez sur **configuration d’Access Edge**.

4.  Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.

5.  Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:
    
      - Pour autoriser l’accès des utilisateurs fédérés pour votre organisation, activez la case à cocher **activer les communications avec les utilisateurs fédérés** .
    
      - Pour désactiver l’accès des utilisateurs fédérés pour votre organisation, décochez la case **activer les communications avec les utilisateurs fédérés** .

6.  Si vous avez activé la case à cocher **activer les communications avec les utilisateurs fédérés** , procédez comme suit:
    
    1.  Si vous voulez prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **activer la découverte de domaines partenaires** .
    
    2.  Si votre organisation prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer le démenti d’archivage aux partenaires fédérés** .

7.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Lync Server 2013, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) dans la documentation de déploiement ou la documentation des opérations. Pour contrôler l’accès pour des domaines fédérés spécifiques, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation relative aux opérations de déploiement ou aux opérations.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la connectivité de Fédération et de messagerie instantanée publique à l’aide d’applets de cmdlet Windows PowerShell

La connectivité de Fédération et de messagerie instantanée publique peut également être gérée à l’aide de Windows PowerShell et de l’applet de connexion Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Pour activer la connectivité de Fédération et de messagerie instantanée publique

  - Pour activer la connectivité de Fédération et de messagerie instantanée publique, définissez la valeur de la propriété **AllowFederatedUsers** sur True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Pour désactiver la connectivité de Fédération et de messagerie instantanée publique

  - Pour désactiver la connectivité de Fédération et de messagerie instantanée publique, définissez la valeur de la propriété **AllowFederatedUsers** sur false ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

