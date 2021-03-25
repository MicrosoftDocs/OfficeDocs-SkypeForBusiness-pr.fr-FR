---
title: Remarques relatives à la jonction du domaine Skype Room System
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: L’administrateur peut découvrir comment joindre un PC d’appliance PC Skype Room System à un domaine Active Directory, ainsi que les considérations à prendre en considération.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117552"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Remarques relatives à la jonction du domaine Skype Room System
 
Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
  
## <a name="domain-joining-considerations"></a>Remarques relatives à la jonction du domaine

Vous pouvez joindre l’appliance PC de Skype Room System au domaine Active Directory ou le laisser dans un groupe de travail. Tenez compte des points suivants avant cette décision :
  
- Le fait de joindre un domaine à l’appliance PC de Skype Room System permet d’importer automatiquement la chaîne de certificats racine privé de votre organisation.
- Le fait de rejoindre un domaine sur l’appliance PC de Skype Room System vous permet d’accorder à des utilisateurs de domaine et à des groupes des droits d’administration. En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.
- Lorsque vous joignez un PC d’équipement de Skype Room System au domaine, vous devez créer une unité organisationnelle distincte afin de pouvoir fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où se trouvent tous les objets machine Skype Room System. Dans ce cas, créez des objets de machine dans l’ou avant de joindre le PC d’appliance Skype Room System au domaine.
- De nombreuses organisations ont les fonctions de groupe suivantes, qui affectent les fonctions d’appliance PC de Skype Room System. Assurez-vous de remplacer ou de bloquer l’héritage de ces éléments de groupe dans le système de salle Skype OU :

  - Délai d’ouverture de sessions (verrouillage automatique)
  - Stratégies liées à la gestion de l’alimentation
  - Besoin d’étapes d’authentification supplémentaires
  - Accès aux lecteurs locaux refusé
  - Inviter les utilisateurs à des connexions réseau lentes
  - Démarrer un programme donné à l’ouverture
  - Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.
  - Push Windows Update to Skype Room System
    
- En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail. Comme pour le client de bureau Microsoft Teams ou Skype Entreprise, vous devez importer manuellement la chaîne de certificats racine sur l’appliance PC de l’appliance Skype Room System. Vous n’êtes pas obligé d’importer la chaîne de certificats racine si votre déploiement utilise un certificat public (par exemple, Confie, VeriSign, et ainsi de suite). 
    
Si vous envisagez d’associer des ordinateurs Skype Room System au domaine, pour éviter de rejoindre l’ordinateur Skype Room System par inadvertance à une ou plusieurs équipes qui ne sont peut-être pas libres d’un groupe de gpos, assurez-vous de participer à l’ou ou correcte. Vous pouvez utiliser l’cmdlet suivante à partir de l’ordinateur Skype Room System pour participer au bon ou et ne reçoit pas d’os de stratégie de groupe qui peuvent bloquer la fonctionnalité LRS. Contactez votre administrateur système ou votre partenaire OEM pour exécuter ces cmdlets :
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Même si vous créez une ou plusieurs stratégies distinctes et bloquez l’héritage, certaines stratégies peuvent entraîner des problèmes à un niveau supérieur. Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies. Pour plus d’informations, [voir Non remplacer par comparaison avec](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) Bloquer l’héritage de stratégie dans la documentation sur les stratégies de groupe.
  
Vous avez peut-être plusieurs approches pour résoudre ces problèmes. Nous vous conseillons de consulter vos experts Active Directory pour vous assurer que vous disposez d’une équipe d’experts qui dispose des paramètres d’environnement de groupe appropriés, ou au moins d’une équipe dans laquelle les stratégies décrites précédemment n’existent pas. Il est déconseillé d’activer la qualité de service (QoS) pour les appareils Skype Room System.

## <a name="related-topics"></a>Rubriques connexes
  
[Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestion de la qualité de service](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)