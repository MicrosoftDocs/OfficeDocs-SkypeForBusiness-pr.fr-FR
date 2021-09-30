---
title: Voir la liste des numéros d’audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment rechercher vos numéros de conférences à partir d’Skype Entreprise Online. '
ms.openlocfilehash: e152cd5d54cd9e1e318027c57cbc4ffda938360b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012098"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Voir la liste des numéros d’audioconférence dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Pour plus d’informations sur les numéros d’audioconférence dans Microsoft Teams, voir [Afficher la liste des numéros d’audioconférence dans Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Lorsque vous définissez des services d’audioconférence pour les utilisateurs de Skype Entreprise, vous pouvez afficher les numéros de téléphone disponibles pour l’audioconférence. Cette liste inséra tous les numéros de téléphone d’audioconférence disponibles pour votre organisation.
  
 **Vous recherchez les prix ?** Consultez [audioconférence] https://www.microsoft.com/microsoft-teams/audio-conferencing) .
  
> [!IMPORTANT]
> **Il n’existe pas de ressource qui contient la liste de tous les numéros de connexion pour l’audioconférence.** Si vous cherchez à savoir si des numéros de téléphone à composer sont disponibles dans votre région ou pays/région, rendez-vous dans le Centre d’administration **Skype Entreprise** Numéros de la voix  >    >  **Téléphone,** cliquez sur Ajouter, puis sur Nouveaux numéros de **service.** Utilisez les listes pour **Pays/région**, **État/région** et **Ville** pour filtrer votre recherche. Par ailleurs, si vous recherchez des numéros de service gratuits, sélectionnez **Gratuit** dans la liste **État/Région.**
  
S'il n'existe qu'un numéro de téléphone disponible pour votre organisation, il est utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. Ce numéro par défaut sera inclus dans les invitations Skype Entreprise réunion.
  
Vous pouvez voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md) afin de modifier le numéro de téléphone à composer pour un seul utilisateur.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone d’audioconférence

1. Connectez-vous avec votre compte scolaire ou scolaire.
    
2. Dans le centre d’administration, > **Skype Entreprise.**
    
3. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez à l’audioconférence   >  **Pont Microsoft,** puis :
    
   - Vous pouvez afficher les numéros de téléphone disponibles pour l’audioconférence.
    
   - Vous pouvez également afficher l’emplacement, la langue principale et les langues secondaires qui seront utilisées par le attendant automatique de l’audioconférence.
    
> [!NOTE]
> Vous pouvez sélectionner Les utilisateurs de l’audioconférence et sélectionner les propriétés de l’utilisateur pour modifier le numéro par défaut en choisissant un nouveau numéro dans la liste des numéros disponibles dans  >   votre organisation. Consultez [Définir les numéros de téléphone inclus dans les invitations.](set-the-phone-numbers-included-on-invites.md) 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Get-⁠CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber).
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d'administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell distante, qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du Centre de téléchargement Microsoft à l’aide du téléchargement et de l’installation du [module Teams PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Voir aussi

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
