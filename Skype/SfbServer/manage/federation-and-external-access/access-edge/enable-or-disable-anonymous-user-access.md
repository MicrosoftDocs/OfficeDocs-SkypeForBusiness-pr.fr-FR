---
title: Activation ou désactivation de l’accès des utilisateurs anonymes
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 35104d7d7128e76f7691a4ddf1ad9693a427eb40
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222750"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Activer ou désactiver l’accès utilisateur anonyme dans Skype pour Business Server

Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’un compte d’utilisateur dans des Services votre organisation de domaine Active Directory ou dans un domaine fédéré pris en charge, mais peuvent être invités à participer à une conférence sur site à distance. En autorisant la participation anonyme aux réunions, vous activez les utilisateurs anonymes (autrement dit, les utilisateurs dont l’identité est vérifiée au moyen de la clé de réunion ou une conférence uniquement) à participer à des réunions. Permettant la participation anonyme nécessite l’activation de votre organisation.

Si vous souhaitez ultérieurement à titre temporaire ou permanent empêcher l’accès des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation. Utilisez la procédure de cette section pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation.

> [!NOTE]  
> En autorisant l’accès utilisateur anonyme pour votre organisation, vous pouvez uniquement définir que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès des utilisateurs anonymes. Les utilisateurs anonymes ne peuvent pas participer à des réunions dans votre organisation jusqu'à ce que vous également configurez au moins une stratégie de conférence et l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes aux réunions sont des utilisateurs qui sont affectés à une stratégie de conférence qui est configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies de conférence pour prendre en charge d’inviter des utilisateurs anonymes, voir [Gérer les stratégies de conférence](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Modifier la Configuration Edge accès**, effectuez l’une des options suivantes :
    
      - Pour activer l’accès utilisateur anonyme pour votre organisation, activez la case à cocher **Activer les communications avec les utilisateurs anonymes** .
    
      - Pour désactiver l’accès utilisateur anonyme pour votre organisation, désactivez la case à cocher **Activer les communications avec les utilisateurs anonymes** .

6.  Cliquez sur **Valider**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès utilisateur anonyme à l’aide des applets de commande Windows PowerShell

Vous pouvez gérer l’accès utilisateur anonyme à l’aide de Windows PowerShell et l’applet de commande **Set-CsAccessEdgeConfiguration** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Pour activer l’accès utilisateur anonyme

  - Pour activer l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Pour désactiver l’accès utilisateur anonyme

  - Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Voir aussi

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
