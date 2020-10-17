---
title: 'Lync Server 2013 : affecter une stratégie de voix par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie de voix par utilisateur.'
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
ms.openlocfilehash: e7ea0b171e10302b4c466187c54324cc2548e821
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563560"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Affecter une stratégie de voix par utilisateur dans Lync Server 2013

 


Les stratégies de voix globale et de niveau site sont automatiquement attribuées à tous les comptes d’utilisateur Lync Server 2013 qui sont activés pour voix entreprise. Vous pouvez également affecter des stratégies de voix à des utilisateurs spécifiques à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell. Utilisez les procédures de cette rubrique pour attribuer explicitement des stratégies par utilisateur aux utilisateurs de Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier l’utilisateur Lync Server** sous **Stratégie de voix**, sélectionnez la stratégie d’utilisateur à appliquer.
    

    > [!NOTE]  
    > Les paramètres <STRONG> &lt; automatiques &gt; </STRONG> appliquent les paramètres de stratégie globale ou de serveur par défaut.



## <a name="assign-per-user-voice-policies"></a>Affecter des stratégies de voix par utilisateur

Vous pouvez affecter des stratégies de voix par utilisateur à l’aide de Windows PowerShell et de la cmdlet **Grant-CsVoicePolicy** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour en savoir plus sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, lisez ce billet de blog Windows PowerShell Lync Server : [démarrage rapide : gestion de Microsoft Lync server 2010 à l’aide de PowerShell à distance](https://go.microsoft.com/fwlink/p/?linkId=255876).

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>Affecter une stratégie de voix par utilisateur à un seul utilisateur

  - La commande suivante assigne la stratégie de voix par utilisateur RedmondVoicePolicy à l’utilisateur Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>Affecter une stratégie de voix par utilisateur à plusieurs utilisateurs

  - Cette commande assigne la stratégie de voix par utilisateur FinanceVoicePolicy à tous les utilisateurs qui ont des comptes dans l’unité d’organisation Finance dans Active Directory. Pour plus d’informations sur le paramètre OU utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>Annuler l’affectation d’une stratégie de voix par utilisateur

  - La commande suivante annule l’assignation d’une stratégie de voix par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Désactivation d’un utilisateur pour voix entreprise dans Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)

