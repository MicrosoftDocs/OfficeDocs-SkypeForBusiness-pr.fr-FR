---
title: Créer des stratégies d'accès externe personnalisées
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype Entreprise En ligne vous permet de créer des stratégies d’accès externe supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinie qui peuvent couvrir la plupart des scénarios.
ms.openlocfilehash: d0ecf5051de17f923983e16f35eb22b66c41571e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619270"
---
# <a name="create-custom-external-access-policies"></a>Créer des stratégies d'accès externe personnalisées

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise En ligne vous permet de créer des stratégies d’accès externe supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies d’accès externe prédéfinie qui peuvent couvrir la plupart des scénarios. Voici ce qui s’intait :
  
- Pas d’accès grand public Skype fédéré ou non (_Tag:NoFederationAndPIC)_
    
- Accès fédéré uniquement (_Balise:FédérationOnly)_
    
- Accès fédéré et grand public _(FederationAndPICDefault)_
    
Les stratégies externes personnalisées vous permettent de créer des polices supplémentaires qui ne sont pas couvertes par les paramètres ci-dessus. Lorsque la stratégie a été créée, vous devez définir tous les paramètres requis et vous n’avez pas pu les modifier ultérieurement. La création de stratégies personnalisées vous permet de contrôler des fonctionnalités telles que l’accès Skype grand public ou une stratégie de désactivation de l’audio/vidéo cloud public, qui n’était pas couverte par des paramètres prédéfinie. Les stratégies d’accès externe personnalisées suivent la même syntaxe que les stratégies de client, de mobilité et de conférence. Pour en savoir plus sur ces paramètres, [cliquez ici.](/previous-versions//mt228132(v=technet.10))
  
Pour ce faire, l’utilisateur doit utiliser une version prise en charge de l’application « Exécuter en un clic » 2016 Skype Entreprise qui la prend en charge. La version minimale suivante du client « Skype Entreprise - Exécuter en un clic 2016 est requise :
  
|**Type**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release pour Canal actuel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (build 7571.2006)  <br/> |
|Canal actuel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (build 7571.2072)  <br/> |
|Canal différé  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures de Skype Entreprise Windows clients Mac seront toujours en mesure de transférer des fichiers. 
  
## <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
1. Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Créer une stratégie d’accès externe personnalisée pour un utilisateur

Pour ce faire, exécutez :
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Rubriques connexes
[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
