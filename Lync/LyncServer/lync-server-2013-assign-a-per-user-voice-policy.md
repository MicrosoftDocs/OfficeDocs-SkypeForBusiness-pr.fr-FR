---
title: 'Lync Server 2013 : affecter une stratégie vocale par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723404"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Affecter une stratégie vocale par utilisateur dans Lync Server 2013

 


Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateurs Lync Server 2013 activés pour Enterprise Voice. Vous pouvez également attribuer des stratégies vocales à des utilisateurs spécifiques à l’aide du panneau de configuration de Lync Server 2013 ou de Lync Server 2013 Management Shell. Suivez les procédures décrites dans cette rubrique pour affecter explicitement des stratégies par utilisateur aux utilisateurs de Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Pour attribuer une stratégie vocale spécifique à l’utilisateur à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie vocale**, sélectionnez la stratégie d’utilisateur que vous voulez appliquer.
    

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent le serveur par défaut ou les paramètres de stratégie globale.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie vocale par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Vous pouvez affecter des stratégies vocales par utilisateur à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsVoicePolicy** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Pour attribuer une stratégie vocale par utilisateur à un utilisateur unique

  - La commande suivante affecte le RedmondVoicePolicy de la stratégie vocale par utilisateur à l’utilisateur Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Pour affecter une stratégie vocale par utilisateur à plusieurs utilisateurs

  - Cette commande affecte le FinanceVoicePolicy de la stratégie vocale par utilisateur à tous les utilisateurs disposant de comptes dans l’unité d’organisation Finance dans Active Directory. Pour plus d’informations sur le paramètre de l’unité d’organisation utilisée dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Pour annuler l’affectation d’une stratégie vocale par utilisateur

  - La commande suivante réattribue toutes les stratégies vocales par utilisateur précédemment affectées à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Désactiver un utilisateur pour voix entreprise dans Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)

