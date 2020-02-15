---
title: 'Lync Server 2013 : affecter une stratégie de plan de numérotation par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043706"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Affectation d’une stratégie de plan de numérotation par utilisateur dans Lync Server 2013

 


Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation au niveau du site si vous n’assignez pas de manière explicite un plan de numérotation utilisateur existant. Si vous voulez utiliser le plan de numérotation global ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Pour affecter un plan de numérotation à l’aide du panneau de configuration Lync Server 2013

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur auquel vous voulez assigner un plan de numérotation.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur **Voix Entreprise**.

8.  Cliquez sur **Stratégie de plan de numérotation**, puis choisissez le plan de numérotation souhaité.

9.  Cliquez sur **Valider**.

Pour plus d’informations sur la configuration des plans de numérotation, voir la rubrique relative à la [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Affecter un plan de numérotation par utilisateur à l’aide des applets de commande Windows PowerShell

Vous pouvez attribuer des plans de numérotation par utilisateur avec Windows PowerShell et l’applet de commande **Grant-CsdialPlan** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Pour affecter un plan de numérotation par utilisateur à un seul utilisateur

  - La commande suivante assigne le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs

  - Cette commande assigne le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Pour annuler l’affectation d’un plan de numérotation par utilisateur

  - La commande suivante annule l’assignation d’un plan de numérotation par utilisateur précédemment assigné à Ken Myer. Une fois l’assignation du plan de numérotation par utilisateur annulée, Ken Myer sera géré automatiquement à l’aide du plan de numérotation global, de son plan de numérotation de site local (s’il en existe un) ou du plan de numérotation à l’échelle du service assigné à son serveur d’inscriptions ou à sa passerelle PSTN. Un plan de numérotation à l’échelle du service est prioritaire par rapport à tout plan de numérotation de site et un plan de numérotation de site est prioritaire par rapport au plan de numérotation global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

