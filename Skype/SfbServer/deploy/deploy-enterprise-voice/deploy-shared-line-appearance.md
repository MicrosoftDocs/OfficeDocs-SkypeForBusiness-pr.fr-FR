---
title: Déployer l’apparence de ligne partagée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: Lisez cette rubrique pour savoir comment déployer l’apparence de ligne partagée (SLA) dans Skype Entreprise Server mise à jour cumulative de novembre 2015. Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un nombre spécifique appelé nombre partagé.
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671590"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Déployer l’apparence de ligne partagée dans Skype Entreprise Server 2015

Lisez cette rubrique pour savoir comment déployer l’apparence de ligne partagée (SLA) dans Skype Entreprise Server mise à jour cumulative de novembre 2015. Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un nombre spécifique appelé nombre partagé.

Pour plus d’informations sur cette fonctionnalité, consultez [Plan for Shared Line Appearance dans Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Shared Line Appearance (SLA) est une nouvelle fonctionnalité de Skype Entreprise Server mise à jour cumulative de novembre 2015. Pour activer cette fonctionnalité, vous devez d’abord avoir déployé cette mise à jour cumulative.

## <a name="install-shared-line-appearance"></a>Installer l’apparence de ligne partagée

1. Après Skype Entreprise Server, la mise à jour cumulative de novembre 2015 est déployée, exécutez le `SkypeServerUpdateInstaller.exe` correctif sur chaque serveur frontal du pool.

2. Le programme d’installation déploie la dernière version de l’application SLA. Toutefois, l’application n’est pas activée par défaut. Elle est activée en suivant les étapes décrites ci-dessous :

    a. Inscrivez le contrat SLA en tant qu’application serveur en exécutant la commande suivante pour chaque pool :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   où %FQDN% est le nom de domaine complet du pool.

    b. Exécutez la commande suivante pour mettre à jour les rôles RBAC pour les applets de commande SLA :

   ```powershell
   Update-CsAdminRole
   ```

    c. Redémarrez tous les serveurs frontaux (service RTCSRV) dans tous les pools où le contrat SLA a été installé et activé :

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>Créer un groupe SLA et y ajouter des utilisateurs

1. Créez le groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    L’applet de commande Set-CsSlaConfiguration marque le compte Voix Entreprise SLAGroup1 en tant qu’entité SLA, et le nombre de SLAGroup1 devient le nombre du groupe SLA. Tous les appels à SLAGroup1 sonnent l’ensemble du groupe SLA.

    L’exemple suivant crée un groupe SLA pour un utilisateur Voix Entreprise existant, SLAGroup1, et utilise le numéro affecté pour SLAGroup1 comme numéro de ligne principale du contrat SLA.

    La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe SLA sur 3 et pour les appels supérieurs à celui-ci afin d’entendre un signal occupé :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Vous pouvez utiliser Set-CsSlaConfiguration pour créer un groupe SLA ou en modifier un existant.

    > [!NOTE]
    > Notez que ce que vous spécifiez doit `-Identity` être un compte d’utilisateur Voix Entreprise valide.

2. Ajoutez des délégués au groupe à l’aide de l’applet de commande [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    L’exemple suivant ajoute un utilisateur au groupe SLA. Chaque utilisateur ajouté au groupe doit être un utilisateur valide Voix Entreprise :

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Répétez l’applet de commande pour chaque utilisateur que vous souhaitez ajouter au groupe. Les utilisateurs ne peuvent appartenir qu’à un seul groupe SLA.

## <a name="configure-the-sla-group-busy-option"></a>Configurer l’option Busy du groupe SLA

- Configurez l’option Busy du groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à transférer au numéro de téléphone 202-555-1234. La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; Dans ce cas, la syntaxe permettant à la personne de recevoir les appels transférés est la même que lorsque vous spécifiez un délégué :  `sip:<NameofDelegate@domain>`. L’autre paramètre possible est  `BusyOption` `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>Configurer l’option d’appel manqué du groupe SLA

1. Configurez l’option d’appel manqué du groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. L’exemple suivant spécifie que les appels manqués doivent être transférés à l’utilisateur nommé  `sla_forward_number`. Les options valides pour le  `-MissedCallOption` paramètre sont `Forward`,  `BusySignal`ou  `Disconnect`. Si vous choisissez  `Forward`, vous devez également inclure le  `-MissedCallForwardTarget` paramètre, avec un numéro d’utilisateur ou de téléphone comme cible :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>Supprimer un délégué d’un groupe

- Supprimez un délégué d’un groupe à l’aide de l’applet de commande [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>Supprimer un groupe SLA

- Supprimez un groupe SLA à l’aide de l’applet de commande [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
