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
ms.openlocfilehash: ffc55984df3b42b06f4db8faa6a286ea41e99480
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568660"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Remarques relatives à la jonction du domaine Skype Room System
 
Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
  
## <a name="domain-joining-considerations"></a>Remarques relatives à la jonction du domaine

Vous pouvez joindre l’appliance Skype salle système PC au domaine Active Directory ou laissez un groupe de travail. Tenez compte des points suivants avant cette décision :
  
- Domaine-joindre l’appliance Skype salle système PC permet d’importation automatique de la chaîne du certificat racine privée de votre organisation.
    
- Domaine-joindre l’appliance Skype salle système PC vous permet d’accorder aux utilisateurs du domaine et les droits d’administration de groupes. En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.
    
- Lorsque vous joignez une appliance Skype salle système PC au domaine, il est nécessaire que vous créez un distinct unité d’organisation (OU), afin que vous pouvez fournir des exclusions de l’objet de stratégie de groupe (GPO) à l’unité d’organisation où résident tous les objets ordinateur Skype salle système. Lorsque vous effectuez cette opération, créer des objets ordinateur dans l’unité d’organisation avant de participer à l’application du système de salle Skype PC au domaine.
    
- Bon nombre d’organisations ont les objets GPO suivants, qui affectent le système de salle Skype application PC fonctionne. Assurez-vous que vous avez remplacer ou bloquer l’héritage de ces objets de stratégie de groupe dans l’unité d’organisation du système de salle de Skype : 
    
  - Délai d’ouverture de sessions (verrouillage automatique)
    
  - Stratégies connexes de gestion de l’alimentation
    
  - Besoin d’étapes d’authentification supplémentaires
    
  - Accès aux lecteurs locaux refusé
    
  - Inviter les utilisateurs à des connexions réseau lentes
    
  - Démarrer un programme donné à l’ouverture
    
  - Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.
    
  - Push Windows Update au système de salle de Skype
    
- En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail. Comme avec le bureau Skype pour client d’entreprise, vous devez importer manuellement la chaîne de certificats racine sur le matériel de système de salle Skype PC. Vous n’êtes pas nécessaire pour importer la chaîne de certificats racine si votre Skype pour le déploiement d’entreprise utilise un certificat public (par exemple, Entrust, VeriSign et ainsi de suite). 
    
Si vous envisagez de participer à des machines Skype salle système au domaine, pour éviter la jonction ordinateur Skype salle système par inadvertance à une unité d’organisation involontaire, qui ne peut être disponible à partir de la stratégie de groupe, assurez-vous que vous participerez à l’unité d’organisation correcte. Vous pouvez utiliser l’applet de commande suivante à partir de l’ordinateur du système de salle Skype pour joindre dans l’unité d’organisation correcte et ne reçoit pas d’objets de stratégie de groupe qui peut se bloquer la fonctionnalité kr. Contactez votre administrateur système ou partenaire OEM pour exécuter ces applets de commande :
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Même si vous créez une unité organisationnelle distincte et que vous bloquez l’héritage, il existe certaines stratégies qui pourraient entraîner des problèmes à un niveau supérieur. Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies. Pour plus d’informations, consultez l’article « No remplacer as par rapport à bloquer l’héritage » dans la documentation de la stratégie de groupe à http://technet.microsoft.com/en-us/library/cc978255.aspx.
  
Vous avez peut-être plusieurs approches pour résoudre ces problèmes. Nous vous conseillons de consulter vos experts Active Directory afin de vous assurer que vous disposez d’une unité organisationnelle aux paramètres GPO appropriés, ou au moins d’une unité organisationnelle dans laquelle les stratégies décrites précédemment n’existent pas. Il est conseillé d’activer la qualité de Service (QoS) pour les périphériques de système de salle Skype.

## <a name="see-also"></a>Voir aussi
  
[Configuration du périphérique : Créer une nouvelle ou en modifier une existant](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestion de la qualité de Service](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
