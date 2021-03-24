---
title: Considérations sur la jointation de domaine Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lisez cette rubrique pour découvrir comment joindre un PC d’appliance Skype Room System à votre domaine.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093568"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Considérations sur la jointation de domaine Skype Room System
 
Lisez cette rubrique pour découvrir comment joindre un PC d’appliance Skype Room System à votre domaine.
  
## <a name="domain-joining-considerations"></a>Considérations sur la jonction de domaine

Vous pouvez joindre le PC appliance Skype Room System au domaine Active Directory ou le laisser dans un groupe de travail. Prenez en compte les points suivants avant de prendre cette décision :
  
- L’association de domaine à l’appliance PC Skype Room System permet d’importer automatiquement la chaîne de certificats racine privée de votre organisation.
    
- Le fait de joindre un domaine à l’appliance PC Skype Room System vous permet d’accorder des droits d’administration aux utilisateurs de domaine et aux groupes. Ainsi, vous n’aurez pas à mémoriser le mot de passe du compte d’administrateur au niveau de l’ordinateur local.
    
- Lorsque vous joignez un PC Appliance Skype Room System au domaine, vous devez créer une unité d’organisation distincte afin de pouvoir fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où résident tous les objets ordinateur Skype Room System. Lorsque vous faites cela, créez des objets d’ordinateur dans l’ou avant de joindre le PC appliance Skype Room System au domaine.
    
- De nombreuses organisations ont les G GPO suivants, qui affectent les fonctions du PC appliance de Skype Room System. Assurez-vous que vous remplacez ou bloquez l’héritage de ces G GPO dans l’ou skype room system : 
    
  - Délai d’ouverture de session (verrouillage automatique)
    
  - Stratégies liées à la gestion de l’alimentation
    
  - Exiger des étapes d’authentification supplémentaires
    
  - Refus d’accès aux lecteurs locaux
    
  - Invite des utilisateurs à des connexions réseau lentes
    
  - Démarrer un certain programme lors de l' logon
    
  - Créez un autre compte d’utilisateur de domaine sur tous les ordinateurs joints au domaine.
    
  - Push Windows Update to Skype Room System
    
- Vous pouvez également décider de laisser l’appliance PC dans le groupe de travail. Comme pour le client Skype Entreprise de bureau, vous devez importer manuellement la chaîne de certificats racine sur le PC d’appliance Skype Room System. Vous n’êtes pas obligé d’importer la chaîne de certificats racine si votre déploiement Skype Entreprise utilise un certificat public (par exemple, Entrust, VeriSign, et ainsi de suite). 
    
Si vous envisagez de joindre des ordinateurs Skype Room System au domaine, pour éviter de joindre par inadvertance un ordinateur Skype Room System à une ouo involontaire, qui n’est peut-être pas gratuite des GOP, assurez-vous que vous rejoignez l’ou correcte. Vous pouvez utiliser l’cmdlet suivante à partir de l’ordinateur Skype Room System pour rejoindre l’ou correcte et ne reçoit pas les G STRATÉGIE de groupe qui peuvent bloquer la fonctionnalité LRS. Contactez votre administrateur système ou votre partenaire OEM pour exécuter ces cmdlet :
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Même si vous créez une ou plusieurs ou entités distinctes et bloquez l’héritage, certaines stratégies peuvent entraîner des problèmes à un niveau supérieur. Une stratégie de groupe sans paramètre de remplacement remplace une ou une autre avec un paramètre Bloquer l’héritage des stratégies. Pour plus d’informations, voir l’article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) dans la documentation de stratégie de groupe.
  
Vous pouvez avoir plusieurs approches pour résoudre ces problèmes. Nous vous conseillons de consulter vos experts Active Directory pour vous assurer que vous disposez d’une ou de plusieurs de vos ux de groupe qui disposent des paramètres DPO appropriés, ou au moins d’une ou plusieurs des stratégies décrites précédemment. Il est recommandé d’activer la qualité de service (QoS) pour les appareils Skype Room System.

## <a name="see-also"></a>Voir aussi
  
[Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestion de la qualité de service](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)