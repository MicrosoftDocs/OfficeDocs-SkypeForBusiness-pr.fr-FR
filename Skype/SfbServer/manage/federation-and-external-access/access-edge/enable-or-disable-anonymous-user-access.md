---
title: Activation ou désactivation de l’accès utilisateur anonyme
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Comment activer et désactiver l’accès des utilisateurs anonymes dans Skype Entreprise Server.
ms.openlocfilehash: 2378ac478faf4f14d7bbfbe0adfdef466a5a8121
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750343"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Activer ou désactiver l’accès des utilisateurs anonymes dans Skype Entreprise Server

Les utilisateurs anonymes sont des utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais peuvent être invités à participer à distance à une conférence sur site. En permettant la participation anonyme aux réunions, vous autorisez les utilisateurs anonymes (c’est-à-dire, les utilisateurs dont l’identité est vérifiée uniquement par le biais de la clé de réunion ou de conférence) à participer aux réunions. L’activation de la participation anonyme nécessite son activation pour votre organisation.

Si vous souhaitez par la suite empêcher temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation. Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation.

> [!NOTE]  
> En activant l’accès des utilisateurs anonymes pour votre organisation, vous spécifiez uniquement que vos serveurs exécutant le service Edge d’accès permettent aux utilisateurs anonymes de prendre en charge l’accès. Les utilisateurs anonymes ne peuvent participer à aucune réunion de votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’avez appliquée à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont ceux qui se voit attribuer une stratégie de conférence configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies de conférence pour prendre en charge l’invitation d’utilisateurs anonymes, voir [Gérer les stratégies de conférence.](../../conferencing/conferencing-policies.md)

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs anonymes pour votre organisation, activez la case à cocher Activer les communications avec **les utilisateurs** anonymes.
    
      - Pour désactiver l’accès des utilisateurs anonymes pour votre organisation, **désactivez** la case à cocher Activer les communications avec les utilisateurs anonymes.

6.  Cliquez sur **Valider**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs anonymes à l’Windows PowerShell cmdlets

Vous pouvez gérer l’accès des utilisateurs anonymes à l’Windows PowerShell et à l’aide de l’cmdlet **Set-CsAccessEdgeConfiguration.** Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Pour activer l’accès des utilisateurs anonymes

  - Pour activer l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($True) :<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Pour désactiver l’accès des utilisateurs anonymes

  - Pour désactiver l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur False ($False) :<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Voir aussi

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
