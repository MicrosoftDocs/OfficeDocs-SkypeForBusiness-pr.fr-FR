---
title: 'Lync Server 2013 : activation ou désactivation de l’accès des utilisateurs anonymes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 076cfd8b787c85ba94d3538c5510d7c12ca11b22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Activer ou désactiver l’accès des utilisateurs anonymes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les utilisateurs anonymes sont des utilisateurs qui ne disposent pas d’un compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais qui peuvent être invités à participer à distance à une conférence locale. En autorisant la participation anonyme aux réunions, vous autorisez les utilisateurs anonymes (c’est-à-dire, les utilisateurs dont l’identité est vérifiée par le biais de la réunion ou de la clé de conférence uniquement) pour participer à des réunions. Autoriser la participation anonyme nécessite de l’activer pour votre organisation.

Si vous souhaitez ultérieurement empêcher temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation. Utilisez la procédure décrite dans cette section pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation.

<div>


> [!NOTE]  
> En activant l’accès des utilisateurs anonymes pour votre organisation, vous spécifiez uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes. Les utilisateurs anonymes ne peuvent pas participer à des réunions dans votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge des utilisateurs anonymes, consultez la rubrique <A href="lync-server-2013-conferencing-policies.md">stratégies de conférence dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès utilisateur anonyme pour votre organisation, activez la case à cocher **autoriser les communications avec des utilisateurs anonymes** .
    
      - Pour désactiver l’accès des utilisateurs anonymes pour votre organisation, désactivez la case à cocher **autoriser les communications avec des utilisateurs anonymes** .

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs anonymes à l’aide des applets de commande Windows PowerShell

Vous pouvez gérer l’accès des utilisateurs anonymes à l’aide de Windows PowerShell et de la cmdlet **Set-CsAccessEdgeConfiguration** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-enable-anonymous-user-access"></a>Pour activer l’accès des utilisateurs anonymes

  - Pour activer l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Pour désactiver l’accès des utilisateurs anonymes

  - Pour désactiver l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

