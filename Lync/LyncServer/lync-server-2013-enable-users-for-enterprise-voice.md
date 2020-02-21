---
title: 'Lync Server 2013 : activation des utilisateurs pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d954fcd121bff2dbc77f390b5cdad1116bb7e7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Activer les utilisateurs pour voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Après avoir installé les fichiers d’un ou de plusieurs serveurs de médiation, configuré le routage des appels sortants et éventuellement déployé une ou plusieurs fonctionnalités voix entreprise avancées, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide de voix entreprise :

<div>


> [!NOTE]  
> Des procédures suivantes, seule la première peut être effectuée à l’aide du panneau de configuration Lync Server. Pour les autres procédures, vous pouvez utiliser uniquement Lync Server Management Shell.



</div>

  - Activez le compte d’utilisateur pour voix entreprise.

  - Module Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.

  - Module Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Pour activer un compte d’utilisateur pour voix entreprise

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur **Voix Entreprise**.

8.  Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, Tél : + 14255550200).

9.  Cliquez sur **Valider**.

Pour terminer l’activation d’un utilisateur pour voix entreprise, assurez-vous que l’utilisateur se voit attribuer une stratégie de voix et un plan de numérotation, qu’il soit global (attribué par défaut) ou spécifique à l’utilisateur.

Par défaut, tous les utilisateurs se voient attribuer une stratégie de voix globale et un plan de numérotation. S’il existe une stratégie de voix ou un plan de numérotation au niveau du site pour le site sur lequel le compte d’utilisateur est hébergé, ces stratégies de site s’appliquent automatiquement à l’utilisateur. Pour appliquer une stratégie vocale ou un plan de numérotation par utilisateur à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan** . Pour plus d’informations, reportez-vous à la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Affectation de stratégie de voix

Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateur qui sont activés pour voix entreprise. Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques. Ces stratégies par utilisateur doivent être explicitement attribuées aux utilisateurs ou aux groupes. Si vous souhaitez utiliser la stratégie globale ou de voix de site pour tous les utilisateurs activés pour voix entreprise, vous pouvez ignorer cette section et continuer à composer le plan de numérotation plus loin dans cette rubrique.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour assigner une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante à l’invite :
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Par exemple :
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    Dans cet exemple, l’utilisateur dont le nom d’affichage est Bob Kelly est affecté à la stratégie de voix portant le nom **VoicePolicyJapan**.

Pour plus d’informations sur l’attribution d’une stratégie de voix spécifique à l’utilisateur ou sur l’exécution de la cmdlet **Grant-CsVoicePolicy** , voir la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Affectation de plan de numérotation

Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation. Les comptes d’utilisateur utiliseront automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation au niveau du site, lorsque vous n’assignez pas explicitement un plan de numérotation par utilisateur existant. Si vous souhaitez utiliser le plan de numérotation de site ou global pour tous les utilisateurs activés pour voix entreprise, vous pouvez ignorer cette section.

<div>

## <a name="to-assign-a-dial-plan"></a>Pour affecter un plan de numérotation

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour assigner un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante à l’invite :
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Par exemple :
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    Dans cet exemple, l’utilisateur dont le nom d’affichage est Bob Kelly est affecté au plan de numérotation de l’utilisateur portant le nom **DialPlanJapan**.

Pour plus d’informations sur l’affectation d’un plan de numérotation utilisateur ou sur l’exécution de la cmdlet **Grant-CsDialPlan** , voir la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactivation d’un utilisateur pour voix entreprise dans Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

