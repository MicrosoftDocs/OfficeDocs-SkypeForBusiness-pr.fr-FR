---
title: Remarques relatives à la jonction du domaine Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
ms.openlocfilehash: 93aa983080ee93f38143224b6c74bdcd6490842c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-domain-joining-considerations"></a>Remarques relatives à la jonction du domaine Skype Room System
 
Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
  
## <a name="domain-joining-considerations"></a>Remarques relatives à la jonction du domaine

Vous pouvez joindre la solution matérielle-logicielle Skype espace système PC au domaine Active Directory ou le laisser dans un groupe de travail. Tenez compte des points suivants avant cette décision :
  
- Domaine-joindre la solution matérielle-logicielle Skype espace système PC permet d’importer automatiquement des chaîne de certificat de racine privée de votre organisation.
    
- Domaine-joindre la solution matérielle-logicielle Skype espace système PC vous permet d’accorder aux utilisateurs du domaine et des droits d’administration des groupes. En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.
    
- Lorsque vous joignez une solution matérielle-logicielle Skype espace système PC sur le domaine, il est nécessaire que vous créez une autre unité d’organisation (OU), afin que vous puissiez fournir des exclusions de l’objet de stratégie de groupe (GPO) pour l’unité d’organisation dans lequel tous les objets d’ordinateur Skype espace système résident. Lorsque vous effectuez cette opération, créez les objets ordinateur dans l’unité d’organisation avant de joindre la solution matérielle-logicielle Skype espace système PC sur le domaine.
    
- De nombreuses organisations possèdent les objets stratégie de groupe, qui affectent des fonctions du matériel PC système de salle de Skype. Assurez-vous que vous substituez ou bloquez l’héritage de ces objets de stratégie de groupe dans l’unité d’organisation du système de salle de Skype : 
    
  - Délai d’ouverture de sessions (verrouillage automatique)
    
  - Stratégies connexes de gestion de l’alimentation
    
  - Besoin d’étapes d’authentification supplémentaires
    
  - Accès aux lecteurs locaux refusé
    
  - Inviter les utilisateurs à des connexions réseau lentes
    
  - Démarrer un programme donné à l’ouverture
    
  - Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.
    
  - Pousser la mise à jour de Windows pour système de salle de Skype
    
- En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail. Comme avec le bureau Skype pour client d’entreprise, vous devez importer manuellement la chaîne de certificats racine sur la solution matérielle-logicielle Skype espace système PC. Vous ne devez pas importer la chaîne de certificats racine si votre Skype pour le déploiement de l’entreprise utilise un certificat public (par exemple, Entrust, VeriSign et ainsi de suite). 
    
Si vous envisagez de rejoindre les machines Skype espace système au domaine, pour éviter l’assemblage machine de Skype espace système par inadvertance à une unité d’organisation inattendue, qui ne peut être exempte de la stratégie de groupe, vérifiez que vous participez à l’unité d’organisation correcte. Vous permet de l’applet de commande suivante à partir de l’ordinateur système d’espace Skype pour jointure dans l’unité d’organisation correcte et ne reçoit pas d’objets de stratégie de groupe susceptibles de bloquer la fonctionnalité LRS. Contactez votre administrateur système ou partenaire OEM pour exécuter ces applets de commande :
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"

```

Même si vous créez une unité organisationnelle distincte et que vous bloquez l’héritage, il existe certaines stratégies qui pourraient entraîner des problèmes à un niveau supérieur. Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies. Pour plus d’informations, consultez l’article « N° substituer par rapport sur Bloquer l’héritage » dans la documentation de la stratégie de groupe à http://technet.microsoft.com/en-us/library/cc978255.aspx.
  
Vous avez peut-être plusieurs approches pour résoudre ces problèmes. Nous vous conseillons de consulter vos experts Active Directory afin de vous assurer que vous disposez d’une unité organisationnelle aux paramètres GPO appropriés, ou au moins d’une unité organisationnelle dans laquelle les stratégies décrites précédemment n’existent pas. Il est conseillé d’activer la qualité de Service (QoS) pour système de salle de Skype.
  

