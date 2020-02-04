---
title: 'Lync Server 2013 : activer les utilisateurs pour voix entreprise'
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
ms.openlocfilehash: 0b851c8807e12456c600b2ca176b0fa5a834f0d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Après avoir installé les fichiers pour un ou plusieurs serveurs de médiation, configuré le routage des appels sortants et éventuellement une ou plusieurs fonctionnalités avancées de voix entreprise, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide d’Enterprise Voice :

<div>


> [!NOTE]  
> Parmi les procédures ci-dessous, seules les premières peuvent être effectuées à l’aide du panneau de configuration de Lync Server. Pour les procédures restantes, vous pouvez uniquement utiliser Lync Server Management Shell.



</div>

  - Activez le compte d’utilisateur voix entreprise voix.

  - (Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.

  - (Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Pour activer un compte d’utilisateur pour voix entreprise

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.

5.  Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur **voix entreprise**.

8.  Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).

9.  Cliquez sur **Valider**.

Pour terminer l’activation d’un utilisateur pour voix entreprise, assurez-vous que l’utilisateur dispose d’une stratégie vocale et d’un plan de numérotation, qu’il s’agisse de global (attribué par défaut) ou d’utilisateur.

Par défaut, tous les utilisateurs se voient affecter une stratégie de voix et un plan de numérotation d’ordre global. S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur. Pour appliquer une stratégie de voix ou un plan de numérotation à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan**. Pour plus d’informations, consultez la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Affectation d’une stratégie de voix

Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateurs activés pour Enterprise Voice. Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques. Ces stratégies utilisateur doivent être affectées explicitement à des utilisateurs ou à des groupes. Si vous souhaitez utiliser la politique globale ou vocale pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section et poursuivre la section affectation de plan de numérotation plus loin dans cette rubrique.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Par exemple :
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly reçoit la politique vocale portant le nom **VoicePolicyJapan**.

Pour plus d’informations sur l’attribution d’une stratégie vocale spécifique à un utilisateur ou sur l’exécution de l’applet de connexion **Grant-CsVoicePolicy** , voir la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Affectation d’un plan de numérotation

Pour achever la configuration de compte d’utilisateur pour les utilisateurs d’Enterprise Voice ou les utilisateurs de conférences rendez-vous, l’utilisateur doit être affecté d’un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas échéant, le plan de numérotation au niveau du site si vous n’affectez pas explicitement un plan de numérotation utilisateur existant. Si vous souhaitez utiliser le plan de numérotation global ou de numérotation de site pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section.

<div>

## <a name="to-assign-a-dial-plan"></a>Pour affecter un plan de numérotation

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Exemple :
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly reçoit le plan de numérotation de l’utilisateur portant le nom **DialPlanJapan**.

Pour plus d’informations sur l’attribution d’un plan de numérotation utilisateur ou sur l’exécution de l’applet de connexion **Grant-CsDialPlan** , voir la documentation de [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactiver un utilisateur pour voix entreprise dans Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

