---
title: Skype à prendre en compte pour la jointation du domaine Room System
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lisez cette rubrique pour découvrir comment joindre un PC Skype Appliance Room System à votre domaine.
---

# <a name="skype-room-system-domain-joining-considerations"></a>Skype à prendre en compte pour la jointation du domaine Room System
 
Lisez cette rubrique pour découvrir comment joindre un PC Skype Appliance Room System à votre domaine.
  
## <a name="domain-joining-considerations"></a>Considérations sur la jonction de domaine

Vous pouvez joindre le PC Skype Room System au domaine Active Directory ou le laisser dans un groupe de travail. Prenez en compte les points suivants avant de prendre cette décision :
  
- Le fait de joindre le Skype PC d’appliance Room System permet d’importer automatiquement la chaîne de certificats racine privée de votre organisation.
    
- Le fait de joindre le Skype PC d’appliance Room System vous permet d’accorder des droits d’administration aux utilisateurs de domaine et aux groupes. Ainsi, vous n’aurez pas à mémoriser le mot de passe du compte d’administrateur au niveau de l’ordinateur local.
    
- Lorsque vous associez un PC appliance Skype Room System au domaine, vous devez créer une unité d’organisation distincte afin de pouvoir fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où résident tous les objets machine Skype Room System. Lorsque vous faites cela, créez des objets machine dans l’ou avant de joindre le PC Skype Room System appliance au domaine.
    
- De nombreuses organisations ont les G GPO suivants, qui affectent Skype fonctions du PC d’appliance Room System. Assurez-vous que vous remplacez ou bloquez l’héritage de ces G GPO dans l’Skype de l’Skype room system : 
    
  - Délai d’ouverture de session (verrouillage automatique)
    
  - Stratégies liées à la gestion de l’alimentation
    
  - Exiger des étapes d’authentification supplémentaires
    
  - Refus d’accès aux lecteurs locaux
    
  - Invite des utilisateurs à des connexions réseau lentes
    
  - Démarrer un certain programme lors de l’logon
    
  - Créez un autre compte d’utilisateur de domaine sur tous les ordinateurs joints au domaine.
    
  - Push Windows Update to Skype Room System
    
- Vous pouvez également décider de laisser l’appliance PC dans le groupe de travail. Comme avec le client Skype Entreprise bureau, vous devez importer manuellement la chaîne de certificats racine sur le PC Skype Room System Appliance. Vous n’êtes pas obligé d’importer la chaîne de certificats racine si votre déploiement Skype Entreprise utilise un certificat public (par exemple, L’uri, VeriSign, et ainsi de suite). 
    
Si vous prévoyez de joindre des ordinateurs Skype Room System au domaine, afin d’éviter de joindre par inadvertance un ordinateur Skype Room System à une ouo involontaire, qui n’est peut-être pas gratuite des GOP, assurez-vous que vous rejoignez l’ou correcte. Vous pouvez utiliser l’cmdlet suivante à partir de l’ordinateur Skype Room System pour rejoindre l’ou correcte et ne reçoit pas les G STRATÉGIE de groupe qui peuvent bloquer la fonctionnalité LRS. Contactez votre administrateur système ou votre partenaire OEM pour exécuter ces cmdlet :
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Même si vous créez une ou plusieurs ou entités distinctes et bloquez l’héritage, certaines stratégies peuvent entraîner des problèmes à un niveau supérieur. Une stratégie de groupe sans paramètre de remplacement remplace une ou une autre avec un paramètre Bloquer l’héritage des stratégies. Pour plus d’informations, voir l’article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) dans la documentation de stratégie de groupe.
  
Vous pouvez avoir plusieurs approches pour résoudre ces problèmes. Nous vous conseillons de consulter vos experts Active Directory pour vous assurer que vous disposez d’une ou de plusieurs de vos ux de groupe qui disposent des paramètres DPO appropriés, ou au moins d’une ou plusieurs des stratégies décrites précédemment. Il est recommandé d’activer la qualité de service (QoS) pour les Skype système de salle.

## <a name="see-also"></a>Voir aussi
  
[Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestion de la qualité de service](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)