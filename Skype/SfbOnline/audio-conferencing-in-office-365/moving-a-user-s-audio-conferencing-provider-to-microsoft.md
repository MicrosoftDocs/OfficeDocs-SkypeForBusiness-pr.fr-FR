---
title: "Déplacement de fournisseur de services d'audioconférence d'un utilisateur à Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. '
ms.openlocfilehash: e28fb11d757265aa74eb559a9d9f4c26661ac26c
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a>Déplacement de fournisseur de services d'audioconférence d'un utilisateur à Microsoft

Pour utiliser la conférence Audio dans Office 365 avec Skype pour les entreprises et les Teams de Microsoft, les utilisateurs de votre organisation doivent disposer d’une licence de **Conférence Audio** affectée ainsi que leur fournisseur de conférence audio doivent être définies à Microsoft. Pour obtenir plus d’informations sur les licences et son coût, reportez-vous à la section [Essayez ou achetez audioconférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a>Pour déplacer un fournisseur de conférence audio d’un utilisateur à Microsoft

Si une licence de **Conférence Audio** est affectée à un utilisateur qui ne possède pas un fournisseur de conférence audio, le fournisseur de l’utilisateur est automatiquement configurée à Microsoft et vous n’avez rien à faire. Si l’utilisateur avait déjà un fournisseur de conférence audio, vous devez modifier le fournisseur de l’utilisateur à Microsoft après l’attribution d’une licence de **Conférence Audio** .
  
Pour définir Microsoft comme le fournisseur de conférence audio pour un utilisateur qui dispose d’une licence de **Conférence Audio** affecté mais utilise un autre fournisseur de conférence audio, procédez comme suit :
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration Business**, passez à **l’audioconférence**.
    
4. Si vous voyez une bannière qui vous avertit qu’il existe des utilisateurs qui ont une **Conférence Audio** licence affectés mais n’avez pas Microsoft défini comme leur fournisseur de conférence audio pour l’instant, cliquez sur **Cliquez ici pour les déplacer**. Si vous ne voyez pas la bannière, dans le **Skype pour le centre d’administration Business** cliquez sur **utilisateurs**et puis sélectionnez le filtre **prête à être déplacée à l’Audio conférence des utilisateurs** .
    
5. Sélectionnez les utilisateurs que vous souhaitez déplacer, puis dans le volet Actions, cliquez sur **Modifier**.
    
6. Sélectionnez **Microsoft** dans la liste **nom du fournisseur** .
    
    > [!NOTE]
    > Lorsque le fournisseur de conférence audio d’un utilisateur est modifié à Microsoft, les informations de conférence audio de l’utilisateur change. Si vous avez besoin de conserver ces informations, veuillez l’enregistrer ailleurs avant de modifier le fournisseur d’un des utilisateurs. 
  
7. Cliquez sur **Enregistrer**.
    
## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Si vous sélectionnez l’utilisateur dans la liste, vous pouvez afficher les informations de conférence audio par défaut de l’utilisateur, mais vous ne pourrez pas voir la code PIN de conférence audio. Vous pouvez réinitialiser la code PIN d’un utilisateur de conférence audio en cliquant sur **Réinitialiser**.
    
- Si vous souhaitez modifier les paramètres de conférence audio pour un utilisateur, vous pouvez sélectionnez l’utilisateur dans la liste puis cliquez sur **Modifier** et apportez vos modifications dans la page de **Propriétés** . 
    
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)

