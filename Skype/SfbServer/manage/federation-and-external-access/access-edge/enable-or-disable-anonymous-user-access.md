---
title: Activer ou désactiver l’accès des utilisateurs anonymes
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
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005999"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Activer ou désactiver l’accès des utilisateurs anonymes dans Skype entreprise Server

Les utilisateurs anonymes sont des utilisateurs qui ne disposent pas d’un compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais qui peuvent être invités à participer à distance à une conférence locale. En autorisant la participation anonyme aux réunions, vous autorisez les utilisateurs anonymes (c’est-à-dire, les utilisateurs dont l’identité est vérifiée par le biais de la réunion ou de la clé de conférence uniquement) pour participer à des réunions. Autoriser la participation anonyme nécessite de l’activer pour votre organisation.

Si vous souhaitez ultérieurement empêcher temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation. Utilisez la procédure décrite dans cette section pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation.

> [!NOTE]  
> En activant l’accès des utilisateurs anonymes pour votre organisation, vous spécifiez uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes. Les utilisateurs anonymes ne peuvent pas participer à des réunions dans votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies de conférence afin de prendre en charge l’invitation des utilisateurs anonymes, consultez la rubrique [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès utilisateur anonyme pour votre organisation, activez la case à cocher **autoriser les communications avec des utilisateurs anonymes** .
    
      - Pour désactiver l’accès des utilisateurs anonymes pour votre organisation, désactivez la case à cocher **autoriser les communications avec des utilisateurs anonymes** .

6.  Cliquez sur **Valider**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs anonymes à l’aide des applets de commande Windows PowerShell

Vous pouvez gérer l’accès des utilisateurs anonymes à l’aide de Windows PowerShell et de la cmdlet **Set-CsAccessEdgeConfiguration** . Vous pouvez exécuter cette cmdlet à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Pour activer l’accès des utilisateurs anonymes

  - Pour activer l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Pour désactiver l’accès des utilisateurs anonymes

  - Pour désactiver l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Voir aussi

[Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
