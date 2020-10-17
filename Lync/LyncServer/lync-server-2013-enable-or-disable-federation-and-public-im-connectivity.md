---
title: 'Lync Server 2013 : activation ou désactivation de la Fédération et de la connectivité PIC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526791"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-24_

La fédération doit être prise en charge pour permettre aux utilisateurs possédant un compte auprès d’un client approuvé ou d’une organisation partenaire, y compris les domaines partenaires et les utilisateurs de fournisseurs de services de messagerie instantanée publics que vous prenez en charge, de collaborer avec des utilisateurs de votre entreprise. La fédération est également nécessaire pour utiliser un fournisseur de service Exchange hébergé afin de procurer une messagerie vocale aux utilisateurs Voix Entreprise dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tel que Microsoft Exchange Online. Une fois que vous avez établi une relation d’approbation avec ces domaines externes, vous pouvez autoriser les utilisateurs de ces domaines à accéder à votre déploiement et à participer à des communications Lync Server. Cette relation de confiance est appelée « fédération » ; elle n’est pas liée à une relation de confiance Active Directory et n’en dépend pas non plus.

Pour prendre en charge l’accès des utilisateurs de domaines fédérés, vous devez activer la fédération. Si vous activez la fédération pour votre entreprise, vous devez également préciser si vous voulez implémenter les options suivantes :

  - **Activer la découverte**     du domaine partenaire Si vous activez cette option, Lync Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés découverts et en limitant ou bloquant le trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés. Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations sur le contrôle de l’accès par les domaines fédérés, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Envoyer une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés**     Une notification d’exclusion de responsabilité est envoyée aux partenaires fédérés pour lesquels l’archivage dans votre déploiement est en place. Si vous prenez en charge l’archivage des communications externes avec des domaines de partenaires fédérés, vous devez activer la notification d’exclusion relative à l’archivage afin de prévenir les partenaires que leurs messages sont archivés.

Si plus tard, vous souhaitez empêcher temporairement ou définitivement des utilisateurs d’accéder aux domaines fédérés, vous pouvez désactiver la fédération pour votre entreprise. Suivez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés dans votre entreprise, en spécifiant notamment les options de fédération que vous souhaitez prendre en charge.

<div>


> [!NOTE]  
> L’activation de la fédération pour votre organisation signifie uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés. Les utilisateurs des domaines fédérés ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de l’accès des utilisateurs fédérés. Les utilisateurs de fournisseurs de services de messagerie instantanée publics ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de la connectivité de messagerie instantanée publique. Lync Server ne peut pas utiliser de service Exchange hébergé pour fournir des services de répondeur automatique, Outlook Voice Access (y compris la messagerie vocale) ou des services de standard automatique aux utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tant que vous n’avez pas configuré de stratégie de messagerie vocale hébergée qui procure des informations de routage. Pour plus d’informations sur la configuration des stratégies de communication avec des utilisateurs de domaines fédérés dans d’autres organisations, voir <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</A> dans la documentation des opérations. Qui plus est, si vous souhaitez prendre en charge les communications avec des utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies à cet effet et configurer la prise en charge des différents fournisseurs de services de votre choix. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013</A> dans la documentation des opérations. Pour plus d’informations sur la création d’une stratégie de messagerie vocale hébergée, voir <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">gérer les stratégies de messagerie vocale hébergées dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre entreprise

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour votre entreprise, activez la case à cocher **Autoriser les communications avec des utilisateurs fédérés**.
    
      - Pour désactiver l’accès des utilisateurs fédérés pour votre entreprise, désactivez la case à cocher **Autoriser les communications avec des utilisateurs fédérés**.

6.  Si vous avez activé la case à cocher **Autoriser les communications avec des utilisateurs fédérés**, procédez comme suit :
    
    1.  Pour prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **Activer la découverte du domaine partenaire**.
    
    2.  Si votre entreprise prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage**.

7.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Lync Server 2013, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, voir [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) dans la documentation de déploiement ou la documentation des opérations. Pour contrôler l’accès à des domaines fédérés spécifiques, reportez-vous à la rubrique [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation sur le déploiement ou les opérations.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la Fédération et de la connectivité PIC à l’aide des applets de commande Windows PowerShell

La Fédération et la connectivité PIC peuvent également être gérées à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Pour activer la Fédération et la connectivité PIC

  - Pour activer la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Pour désactiver la Fédération et la connectivité PIC

  - Pour désactiver la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

