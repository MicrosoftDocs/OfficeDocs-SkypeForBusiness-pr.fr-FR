---
title: 'Lync Server 2013 : déploiement de l’apparence des lignes partagées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1523a48b5d9056b1cca532a7edb1c826af841b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Déployer une apparence de ligne partagée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-06-13_

Consultez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans Lync Server 2013, mise à jour cumulative avril 2016. Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».

Pour plus d’informations sur cette fonctionnalité, reportez-vous à la rubrique [plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

L’apparence de ligne partagée (SLA) est une nouvelle fonctionnalité de Lync Server 2013, mise à jour cumulative avril 2016. Pour activer cette fonctionnalité, vous devez d’abord déployer cette mise à jour cumulative.

<div>

## <a name="install-shared-line-appearance"></a>Installation de l’apparence des lignes partagées

1.  Une fois que Lync Server 2013, mise à jour cumulative avril 2016 est déployé, l’application SLA n’est pas activée par défaut. Pour activer l’application, procédez comme suit :
    
    1.  Inscrivez le contrat SLA en tant qu’application serveur en exécutant la commande suivante pour chaque pool :
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        où% FQDN% est le nom de domaine complet du pool.
    
    2.  Exécutez la commande suivante pour mettre à jour les rôles RBAC pour les cmdlets SLA :
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Redémarrez tous les serveurs frontaux (RTCSRV service) dans tous les pools où le contrat SLA a été installé et activé :
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Créer un groupe de SLA et y ajouter des utilisateurs

1.  Créez le groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    La cmdlet Set-CsSlaConfiguration marque le compte voix entreprise SLAGroup1 comme entité SLA et le nombre d’SLAGroup1 devient le numéro du groupe SLA. Tous les appels vers SLAGroup1 sonneront dans l’ensemble du groupe SLA.
    
    L’exemple suivant crée un groupe de SLA pour un utilisateur voix entreprise existant, SLAGroup1, et utilise le numéro attribué à SLAGroup1 comme numéro de la forme de service SLA.
    
    La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de SLA sur 3, et pour les appels au-delà de celui pour écouter un signal occupé :
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Vous pouvez utiliser SET-CsSlaConfiguration pour créer un nouveau groupe de SLA ou en modifier un existant.
    
    <div>
    

    > [!NOTE]  
    > Notez que ce que vous spécifiez pour doit être un compte d’utilisateur activé pour <CODE>-Identity</CODE> voix entreprise existant valide.

    
    </div>

2.  Ajoutez des délégués au groupe à l’aide de la cmdlet [Add-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    L’exemple suivant ajoute un utilisateur au groupe SLA. Chaque utilisateur ajouté au groupe doit être un utilisateur compatible voix entreprise valide :
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Répétez l’applet de commande pour chaque utilisateur que vous souhaitez ajouter au groupe. Les utilisateurs ne peuvent appartenir qu’à un seul groupe SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Configurer l’option de disponibilité du groupe SLA

1.  Configurez l’option de disponibilité du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à transmettre au numéro de téléphone 202-555-1234. La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; dans ce cas, la syntaxe de la personne qui reçoit les appels transférés est la même que lorsque vous spécifiez un délégué `sip:<NameofDelegate@domain>`:. L’autre paramètre possible pour `BusyOption` est `Voicemail`le suivant :
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Configurer l’option d’appel manqué du groupe SLA

1.  Configurez l’option d’appel manqué du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    L’exemple suivant spécifie que les appels manqués doivent être transférés à l' `sla_forward_number`utilisateur nommé. Les options valides pour `-MissedCallOption` le paramètre `Forward`sont `BusySignal`, ou `Disconnect`. Si vous le `Forward`souhaitez, vous devez également inclure `-MissedCallForwardTarget` le paramètre, avec un utilisateur ou un numéro de téléphone comme cible :
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Supprimer un délégué d’un groupe

1.  Supprimer un délégué d’un groupe à l’aide de l’applet de commande [Remove-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Par exemple :
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>Supprimer un groupe SLA

1.  Supprimez un groupe de SLA à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Par exemple :
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

