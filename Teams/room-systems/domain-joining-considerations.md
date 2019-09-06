---
title: Remarques relatives à la jonction du domaine Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
ms.openlocfilehash: be8fd60b67efb356e09678eef21fbfab425ce304
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774641"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Remarques relatives à la jonction du domaine Skype Room System
 
Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
  
## <a name="domain-joining-considerations"></a>Remarques relatives à la jonction du domaine

Vous pouvez rejoindre le PC de l’application Skype Room sur le domaine Active Directory ou la laisser dans un groupe de travail. Tenez compte des points suivants avant cette décision :
  
- La participation à un domaine avec l’application Skype Room System permet d’importer automatiquement la chaîne de certificats racine privés de votre organisation.
- La participation à un domaine avec l’application Skype Room System appliance vous permet d’accorder aux utilisateurs de domaine et aux groupes des droits d’administration. En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.
- Lorsque vous rejoignez un ordinateur du système de salle Skype pour le domaine, vous devez créer une unité d’organisation (UO) distincte, afin de fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où se trouvent tous les objets de l’ordinateur de bureau Skype. Lorsque vous procédez ainsi, créez des objets machine dans l’unité d’organisation avant de joindre le PC du système de salle Skype au domaine.
- De nombreuses organisations possèdent les objets de stratégie de groupe suivants qui concernent les fonctions PC de l’appliance de salle Skype. Assurez-vous de remplacer ou de bloquer l’héritage de ces objets de stratégie de groupe dans l’unité d’organisation de votre système de salle Skype :

  - Délai d’ouverture de sessions (verrouillage automatique)
  - Stratégies connexes de gestion de l’alimentation
  - Besoin d’étapes d’authentification supplémentaires
  - Accès aux lecteurs locaux refusé
  - Inviter les utilisateurs à des connexions réseau lentes
  - Démarrer un programme donné à l’ouverture
  - Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.
  - Diffuser Windows Update vers le système de salle Skype
    
- En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail. Comme avec la version de bureau de Microsoft teams ou du client Skype entreprise, vous devez importer manuellement la chaîne de certificats racine sur le PC du système de salle Skype. Vous n’êtes pas tenu d’importer la chaîne de certificats racines si votre déploiement utilise un certificat public (par exemple, Entrust, VeriSign, etc.). 
    
Si vous envisagez de joindre les machines de votre système de salle Skype à votre domaine, dans le cas d’une UO involontaire qui n’est pas disponible pour les objets de stratégie de groupe, assurez-vous de rejoindre l’UO correcte. Vous pouvez utiliser l’applet de commande suivante depuis l’ordinateur système de salle Skype pour rejoindre l’UO correcte et ne pas recevoir d’objets de stratégie de groupe qui peuvent bloquer la fonctionnalité LRS. Contactez votre administrateur système ou partenaire OEM pour exécuter ces applets de commande :
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Même si vous créez une unité organisationnelle distincte et que vous bloquez l’héritage, il existe certaines stratégies qui pourraient entraîner des problèmes à un niveau supérieur. Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies. Pour plus d’informations, reportez-vous à l’article [aucun remplacement par rapport à l’héritage de la stratégie bloquer](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) dans la documentation de la stratégie de groupe.
  
Vous avez peut-être plusieurs approches pour résoudre ces problèmes. Nous vous conseillons de consulter vos experts Active Directory afin de vous assurer que vous disposez d’une unité organisationnelle aux paramètres GPO appropriés, ou au moins d’une unité organisationnelle dans laquelle les stratégies décrites précédemment n’existent pas. Il est recommandé d’activer la qualité de service (QoS) pour les appareils système de salle Skype.

## <a name="see-also"></a>Voir aussi
  
[Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gestion de la qualité de service](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
