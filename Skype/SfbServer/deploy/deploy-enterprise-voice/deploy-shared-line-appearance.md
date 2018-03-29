---
title: Déploiement du mode partage de lignes dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Pour découvrir comment déployer le mode partage de lignes dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015, reportez-vous à cette rubrique. Le mode partage de lignes est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».
ms.openlocfilehash: ba7ca76c9ef0c6ed49ba26205df69e7840ec75d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Déploiement du mode partage de lignes dans Skype Entreprise Server 2015
 
Pour découvrir comment déployer le mode partage de lignes dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015, reportez-vous à cette rubrique. Le mode partage de lignes est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ». 
  
Pour plus d’informations sur cette fonctionnalité, voir [planification de l’apparence de la ligne partagée dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).
  
Apparence de ligne partagé (SLA) est une nouvelle fonctionnalité dans Skype pour Business Server, novembre 2015 mise à jour Cumulative. Pour activer cette fonctionnalité, vous devez d’abord avoir déployé cette mise à jour cumulative.
  
### <a name="install-shared-line-appearance"></a>Installation du mode partage de lignes

1. Une fois Skype pour Business Server, novembre 2015 mise à jour Cumulative est déployé, exécutez le `SkypeServerUpdateInstaller.exe` correctif sur chaque serveur frontal dans le pool.
    
2. Le programme d’installation déploiera la version la plus récente de l’application Mode partage de lignes, mais l’application n’est pas activée par défaut. Elle est activée en suivant la procédure décrite ci-dessous :
    
    a. Enregistrez le mode partage de lignes comme application serveur en exécutant la commande ci-dessous pour chaque pool :
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   où %FQDN% est le nom de domaine complet du pool. 
    
    b. Exécutez la commande ci-dessous pour mettre à jour les rôles RBAC pour les applets de commande du mode partage de lignes : 
    
   ```
   Update-CsAdminRole 
   ```

    c. Redémarrez tous les serveurs frontaux (service RTCSERV) dans tous les pools où le mode partage de lignes a été installé et activé :
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Créez un groupe de mode partage de lignes et ajoutez-y des utilisateurs.

1. Créez le groupe de SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -MaxNumberOfCalls <Number> -BusyOption
          <BusyOnBusy|Voicemail|Forward> [-Target
          <TargetUserOrPhoneNumber>]
  ```

    L’applet de commande Set-CsSlaConfiguration marque le compte SLAGroup1 de Voix Entreprise en tant qu’entité de mode partage de lignes, et le numéro de SLAGroup1 devient le numéro du groupe de mode partage de lignes. Tous les appels vers SLAGroup1 sonneront chez l’ensemble du groupe de mode partage de lignes.
    
    L’exemple ci-dessous crée un groupe de mode partage de lignes pour un utilisateur Voix Entreprise existant, SLAGroup1, et utilise le numéro attribué pour SLAGroup1 comme numéro de ligne principale du mode partage de lignes. 
    
    La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de mode partage de lignes sur 3. Les appels qui dépassent cette limitent entendront une tonalité Occupé :
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
          -BusyOption BusyOnBusy
  ```

    Vous pouvez utiliser Set-CsSlaConfiguration pour créer un groupe de mode partage de lignes ou modifier un groupe existant.
    
    > [!NOTE]
    > Notez que ce que vous spécifiez pour `-Identity` doit être un compte d’utilisateur de Voix Entreprise existant valide.
  
2. Ajouter des délégués à l’aide de l’applet de commande [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) pour le groupe :
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    L’exemple ci-dessous permet d’ajouter un utilisateur au groupe de mode partage de lignes. Chaque utilisateur ajouté au groupe doit être un utilisateur valide de Voix Entreprise :
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate1@contoso.com
  ```

    Répétez l’applet de commande pour chaque utilisateur que vous voulez ajouter au groupe. Les utilisateurs peuvent seulement appartenir à un seul groupe de mode de partage de lignes.
    
### <a name="configure-the-sla-group-busy-option"></a>Configuration de l’option Occupé du groupe de mode partage de lignes

- Configurer le contrat SLA Option occupé de groupe à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    L’exemple suivant définit des appels qui dépassent le nombre maximal d’appels simultanés à transmettre à la 202-555-1234 numéro téléphone. La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; Dans ce cas, la syntaxe pour la personne qui doit recevoir le transfert des appels est la même que lorsque vous spécifiez un délégué : `sip:<NameofDelegate@domain>`. L’autre paramètre possible de `BusyOption` est `Voicemail`:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
          -Target tel:+2025551234]
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configuration de l’option Appel manqué du groupe de mode partage de lignes

1. Configurer le groupe de SLA manquées appel Option à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
          -MissedCallOption <Option> -MissedCallForwardTarget
          <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. L’exemple suivant spécifie que les appels sont transmis à l’utilisateur nommé `sla_forward_number`. Les options valides pour le `-MissedCallOption` paramètre sont `Forward`, `BusySignal`, ou `Disconnect`. Si vous choisissez `Forward`, vous devez également inclure le `-MissedCallForwardTarget` paramètre avec un utilisateur ou numéro de téléphone comme cible :
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
          Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
    -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a>Suppression d’un délégué d’un groupe

- Supprimer un délégué d’un groupe à l’aide de l’applet de commande [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    Par exemple :
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Suppression d’un groupe de mode partage de lignes

- Supprimer un groupe de SLA à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
          
  ```

    Par exemple : 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


