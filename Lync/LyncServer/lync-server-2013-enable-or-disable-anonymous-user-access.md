---
title: 'Lync Server 2013 : Activation ou désactivation de l’accès des utilisateurs anonymes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Les utilisateurs anonymes sont des utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou qui sont invités à participer à distance dans une conférence locale. La participation anonyme aux réunions vous permet d’activer les utilisateurs anonymes (c’est-à-dire les utilisateurs dont l’identité est vérifiée uniquement via la réunion ou la clé de conférence) pour participer aux réunions. L’activation de la participation anonyme exige de l’activer pour votre organisation.

Si vous souhaitez suspendre temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation. Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation, suivez la procédure décrite dans cette section.

<div>


> [!NOTE]  
> L’activation de l’accès anonyme aux utilisateurs de votre organisation consiste uniquement à indiquer que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes. Les utilisateurs anonymes ne peuvent pas participer à une réunion au sein de votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est affectée et qui est configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge de l’invitation d’utilisateurs anonymes, voir <A href="lync-server-2013-conferencing-policies.md">stratégies de conférence dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis cliquez sur **configuration d’Access Edge**.

4.  Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.

5.  Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:
    
      - Pour activer l’accès anonyme aux utilisateurs de votre organisation, activez la case à cocher **activer les communications avec les utilisateurs anonymes** .
    
      - Pour désactiver l’accès anonyme aux utilisateurs de votre organisation, décochez la case **activer les communications avec les utilisateurs anonymes** .

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès utilisateur anonyme à l’aide des cmdlets Windows PowerShell

Vous pouvez gérer l’accès utilisateur anonyme à l’aide de Windows PowerShell et de l’applet **de connexion Set-CsAccessEdgeConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-enable-anonymous-user-access"></a>Pour autoriser l’accès des utilisateurs anonymes

  - Pour autoriser l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Pour désactiver l’accès des utilisateurs anonymes

  - Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false):
    
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

