---
title: Activation ou désactivation de l’accès des utilisateurs anonymes
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818405"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Activation ou désactivation de l’accès anonyme aux utilisateurs dans Skype entreprise Server

Les utilisateurs anonymes sont des utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou qui sont invités à participer à distance dans une conférence locale. La participation anonyme aux réunions vous permet d’activer les utilisateurs anonymes (c’est-à-dire les utilisateurs dont l’identité est vérifiée uniquement via la réunion ou la clé de conférence) pour participer aux réunions. L’activation de la participation anonyme exige de l’activer pour votre organisation.

Si vous souhaitez suspendre temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation. Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation, suivez la procédure décrite dans cette section.

> [!NOTE]  
> L’activation de l’accès anonyme aux utilisateurs de votre organisation consiste uniquement à indiquer que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes. Les utilisateurs anonymes ne peuvent pas participer à une réunion au sein de votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est affectée et qui est configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge de l’invitation d’utilisateurs anonymes, voir [gérer les stratégies de conférence](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis cliquez sur **configuration d’Access Edge**.

4.  Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.

5.  Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès anonyme aux utilisateurs de votre organisation, activez la case à cocher **activer les communications avec les utilisateurs anonymes** .
    
      - Pour désactiver l’accès anonyme aux utilisateurs de votre organisation, décochez la case **activer les communications avec les utilisateurs anonymes** .

6.  Cliquez sur **Valider**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès utilisateur anonyme à l’aide des cmdlets Windows PowerShell

Vous pouvez gérer l’accès utilisateur anonyme à l’aide de Windows PowerShell et de l’applet **de connexion Set-CsAccessEdgeConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Pour autoriser l’accès des utilisateurs anonymes

  - Pour autoriser l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Pour désactiver l’accès des utilisateurs anonymes

  - Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Voir aussi

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
