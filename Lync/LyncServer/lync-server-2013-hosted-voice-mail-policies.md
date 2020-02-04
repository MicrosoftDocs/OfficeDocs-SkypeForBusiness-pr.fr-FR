---
title: 'Lync Server 2013 : Stratégies de messagerie vocale hébergées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Stratégies de messagerie vocale hébergées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Une *stratégie de messagerie vocale hébergée* fournit des informations à l’application de routage de l’ExUM de Lync Server 2013 sur l’emplacement de routage des appels pour les utilisateurs dont la boîte aux lettres est située sur un service Exchange hébergé.

<div>


> [!NOTE]  
> Les stratégies de messagerie vocale hébergées sont uniquement requises pour l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée. Elles ne sont pas nécessaires pour l’intégration à la messagerie unifiée Exchange locale.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Étendue de la stratégie de messagerie vocale hébergée

L’étendue de la stratégie de messagerie vocale hébergée détermine le niveau hiérarchique auquel la stratégie s’applique. Vous pouvez configurer des stratégies de messagerie vocale hébergées avec les niveaux d’étendue suivants :

  - La stratégie *globale* peut potentiellement affecter tous les utilisateurs dans le déploiement de Lync Server 2013. Si un utilisateur est autorisé à utiliser l’accès à la messagerie unifiée Exchange hébergé sans avoir reçu une stratégie individuelle et qu’aucune stratégie de site ne lui a été attribuée, la politique globale s’applique. La stratégie globale est installée avec Lync Server 2013. Vous pouvez le modifier en fonction de vos besoins, mais vous ne pouvez pas le renommer ou le supprimer.

  - Une stratégie de *site* peut affecter tous les utilisateurs qui sont hébergés sur le site pour lesquels la stratégie est définie. Si un utilisateur est configuré pour l’accès à la messagerie unifiée Exchange hébergé sans avoir reçu une stratégie par utilisateur, la stratégie de site s’applique.

  - Une stratégie *par utilisateur* peut affecter uniquement des utilisateurs ou des groupes spécifiques. Pour appliquer une stratégie par utilisateur, vous devez affecter explicitement la stratégie à des utilisateurs, des groupes et des objets de contact individuels.

<div>


> [!NOTE]  
> Dans la plupart des cas, une seule stratégie de messagerie vocale hébergée est requise. Vous pouvez souvent modifier la politique globale en fonction de vos besoins. Si vous déployez plusieurs stratégies de messagerie vocale hébergées, toutes les stratégies de ce type ont une étendue par utilisateur.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Attributs de la stratégie de messagerie vocale hébergée

Une stratégie de messagerie vocale définit les deux attributs insérés par l’application de routage Lync Server 2013 dans l’URI de requête d’un message d’invitation qui est envoyé à l’implémentation de MU Exchange hébergée :

  - **Destination :** Nom de domaine complet (FQDN) du service de messagerie unifiée Exchange hébergé. Cette valeur est utilisée par le serveur Edge Lync Server local à des fins de routage.
    
    <div>
    

    > [!NOTE]  
    > Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.

    
    </div>

  - **Organisation :** Nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé qui héberge les boîtes aux lettres des utilisateurs de Lync Server 2013. Une stratégie de messagerie vocale peut contenir plusieurs organisations. S’il s’agit de plusieurs organisations, cet attribut doit être une liste séparée par des virgules des clients du serveur Exchange qui se trouvent à l’origine de vos boîtes aux lettres d’utilisateur Lync Server 2013.

<div>


> [!NOTE]  
> L’administrateur client de votre service UM Exchange hébergé fournit les valeurs nécessaires à votre destination et aux paramètres d’attribut de votre organisation. Pour configurer votre stratégie, vous devez exécuter l’applet de nouvelle applet de nouveau-CsHostedVoicemailPolicy ou utiliser l’applet de passe Set-CsHostedVoicemailPolicy pour en modifier une qui existe (par exemple, la stratégie globale).



</div>

Pour plus d’informations sur la gestion des stratégies de messagerie vocale hébergée, consultez la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - Nouveau-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Affectation de stratégie de messagerie vocale par utilisateur

Si votre stratégie de messagerie vocale hébergée est définie avec une étendue par utilisateur, vous devez l’attribuer explicitement. Vous pouvez exécuter l’applet de passe Grant-CsHostedVoicemailPolicy pour affecter la stratégie à des utilisateurs ou groupes individuels.

Pour plus d’informations sur l’attribution ou la suppression d’une stratégie de messagerie vocale hébergée par utilisateur, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

