---
title: 'Lync Server 2013: affecter une stratégie de plan de numérotation par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f9bca09515daba6db7e072625d5b4a217d37cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846938"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Affecter une stratégie de plan de numérotation par utilisateur dans Lync Server 2013

 


Pour achever la configuration de compte d’utilisateur pour les utilisateurs d’Enterprise Voice ou les utilisateurs de conférences rendez-vous, l’utilisateur doit être affecté d’un plan de numérotation. Les comptes d’utilisateurs utiliseront automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation de niveau de site lorsque vous n’affectez pas explicitement un plan de numérotation par utilisateur existant. Si vous souhaitez utiliser le plan de numérotation global ou de numérotation de site pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Pour affecter un plan de numérotation à l’aide du panneau de configuration de Lync Server 2013

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.

5.  Dans la table, cliquez sur le compte d’utilisateur auquel vous voulez attribuer un plan de numérotation.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur **voix entreprise**.

8.  Cliquez sur **stratégie de plan**de numérotation, puis sélectionnez le plan de numérotation de votre choix.

9.  Cliquez sur **Valider**.

Pour plus d’informations sur la configuration des plans de numérotation, reportez-vous à la rubrique [configuration de plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Affectation d’un plan de numérotation par utilisateur à l’aide des cmdlets Windows PowerShell

Vous pouvez affecter des plans de numérotation par utilisateur avec Windows PowerShell et l’applet **de connexion Grant-CsdialPlan** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Pour affecter un plan de numérotation par utilisateur à un seul utilisateur

  - La commande suivante attribue le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs

  - Cette commande affecte le plan de numérotation RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Pour annuler l’affectation d’un plan de numérotation par utilisateur

  - La commande suivante réattribue un plan de numérotation par utilisateur précédemment attribué à Ken Myer. Lorsque le plan de numérotation par utilisateur n’est pas affecté, Ken Myer sera automatiquement géré à l’aide du plan de numérotation globale, de son plan de numérotation de site local (s’il en existe une) ou du plan de numérotation d’étendue de service affecté à son bureau d’enregistrement ou à ma passerelle PSTN. Le plan de numérotation de l’étendue du service est prioritaire sur n’importe quel plan de numérotation de site, et un plan de numérotation est prioritaire sur le plan de numérotation global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

