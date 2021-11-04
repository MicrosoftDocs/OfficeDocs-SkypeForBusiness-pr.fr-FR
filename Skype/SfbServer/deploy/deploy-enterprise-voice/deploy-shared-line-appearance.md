---
title: Déployer l’apparence des lignes partagées Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lisez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015. Le SLA est une fonctionnalité qui permet de gérer plusieurs appels sur un numéro spécifique appelé numéro partagé.
ms.openlocfilehash: edf731976ae9fbf36f99266f0d993c9e4e78fa34
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749443"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Déployer l’apparence des lignes partagées Skype Entreprise Server 2015

Lisez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015. Le SLA est une fonctionnalité qui permet de gérer plusieurs appels sur un numéro spécifique appelé numéro partagé.

Pour plus d’informations sur cette fonctionnalité, voir [Plan for Shared Line Appearance in Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Le partage de lignes est une nouvelle fonctionnalité de la mise à jour cumulative Skype Entreprise Server novembre 2015. Pour activer cette fonctionnalité, vous devez d’abord avoir déployé cette mise à jour cumulative.

### <a name="install-shared-line-appearance"></a>Installer l’apparence des lignes partagées

1. Après Skype Entreprise Server, la mise à jour cumulative de novembre 2015 est déployée, exécutez le correctif sur chaque serveur `SkypeServerUpdateInstaller.exe` frontal du pool.

2. Le programme d’installation déploiera la dernière version de l’application SLA, mais l’application n’est pas activée par défaut. Il est activé en suivant les étapes décrites ci-dessous :

    a. Inscrivez le SLA en tant qu’application serveur en exécutant la commande suivante pour chaque pool :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   où %FQDN% est le nom de domaine complet du pool.

    b. Exécutez la commande suivante pour mettre à jour les rôles RBAC pour les cmdlets SLA :

   ```powershell
   Update-CsAdminRole
   ```

    c. Redémarrez tous les serveurs frontux (service RTCSRV) dans tous les pools où le SLA a été installé et activé :

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Créer un groupe de SLA et y ajouter des utilisateurs

1. Créez le groupe SLA à l’aide de l’cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    LSet-CsSlaConfiguration cmdlet marque le compte Voix Entreprise SLAGroup1 en tant qu’entité SLA, et le nombre de SLAGroup1 devient le numéro du groupe de SLA. Tous les appels à SLAGroup1 sonnent dans l’ensemble du groupe SLA.

    L’exemple suivant crée un groupe de SLA pour un utilisateur Voix Entreprise existant, SLAGroup1, et utilise le numéro affecté à SLAGroup1 comme numéro de ligne principale du SLA.

    La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de SLA sur 3, et pour les appels qui dépassent cette valeur pour écouter une signal occupé :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Vous pouvez utiliser Set-CsSlaConfiguration pour créer un groupe de SLA ou en modifier un existant.

    > [!NOTE]
    > Notez que ce que vous spécifiez doit être un compte d’utilisateur `-Identity` Voix Entreprise valide.

2. Ajoutez des délégués au groupe à l’aide de l’cmdlet [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    L’exemple suivant ajoute un utilisateur au groupe SLA. Chaque utilisateur ajouté au groupe doit être un utilisateur Voix Entreprise valide :

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Répétez la cmdlet pour chaque utilisateur que vous souhaitez ajouter au groupe. Les utilisateurs ne peuvent appartenir qu’à un seul groupe de SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurer le groupe SLA Busy Option

- Configurez le groupe SLA Busy Option à l’aide de [l';set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à être transmis au numéro de téléphone 202-555-1234. La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone . dans ce cas, la syntaxe de la personne qui reçoit les appels transmis est la même que lorsque vous spécifiez un délégué :  `sip:<NameofDelegate@domain>` . L’autre paramètre possible `BusyOption` est : `Voicemail`

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurer l’option d’appel manqué du groupe SLA

1. Configurez l’option d’appel manqué du groupe SLA à l’aide de l’cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. L’exemple suivant spécifie que les appels manqués doivent être transmis à l’utilisateur nommé  `sla_forward_number` . Les options valides pour  `-MissedCallOption` le paramètre sont , ou `Forward`  `BusySignal`  `Disconnect` . Si vous  `Forward` choisissez, vous devez également inclure le paramètre, avec un utilisateur ou  `-MissedCallForwardTarget` un numéro de téléphone comme cible :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Supprimer un délégué d’un groupe

- Supprimez un délégué d’un groupe à l’aide de l’cmdlet [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Supprimer un groupe de SLA

- Supprimez un groupe de SLA à l’aide de l’cmdlet [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```