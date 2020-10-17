---
title: 'Lync Server 2013 : stratégies de messagerie vocale hébergées'
description: 'Lync Server 2013 : stratégies de messagerie vocale hébergées.'
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
ms.openlocfilehash: 57461f4ffd2c6f2cd733dd7ec2c945c9e7b801c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550100"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Stratégies de messagerie vocale hébergées dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Une *stratégie de messagerie vocale hébergée* fournit des informations à l’application de routage ExUM de Lync Server 2013 sur l’emplacement des appels pour les utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé.

<div>


> [!NOTE]  
> Les stratégies de messagerie vocale hébergées ne sont requises que pour l’intégration de Lync Server 2013 avec la messagerie unifiée Exchange hébergée. Elles ne sont pas nécessaires dans le cas d’une intégration à la messagerie Exchange sur site.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Étendue des stratégies de messagerie vocale hébergée

L’étendue des stratégies de messagerie vocale hébergée détermine le niveau hiérarchique d’application des stratégies. Vous pouvez configurer les stratégies de messagerie vocale hébergée avec les niveaux d’étendue suivants :

  - La stratégie *globale* peut potentiellement affecter tous les utilisateurs dans le déploiement Lync Server 2013. Si un utilisateur est activé pour l’accès à la messagerie unifiée Exchange hébergée, mais qu’aucune stratégie par utilisateur ne lui a été attribuée, et si aucune stratégie de site n’a été attribuée au site de l’utilisateur, la stratégie globale s’applique. La stratégie globale est installée avec Lync Server 2013. Vous pouvez la modifier en fonction de vos besoins, mais pas la renommer ni la supprimer.

  - Une stratégie de *site* peut concerner tous les utilisateurs qui sont hébergés sur le site pour lequel la stratégie est définie. Si aucune stratégie par utilisateur n’a été attribuée à un utilisateur qui est configuré pour l’accès à la messagerie unifiée Exchange hébergée, la stratégie de site s’applique.

  - Une stratégie *par utilisateur* peut uniquement affecter des utilisateurs individuels ou des groupes. Pour appliquer une stratégie par utilisateur, vous devez l’attribuer explicitement à des utilisateurs individuels, des groupes et des objets contact.

<div>


> [!NOTE]  
> Généralement, une seule stratégie de messagerie vocale hébergée est requise. Dans de nombreux cas, vous pouvez modifier la stratégie globale pour qu’elle réponde à vos besoins. Si vous déployez plusieurs stratégies de messagerie vocale hébergée, toutes ont une étendue par utilisateur.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Attributs des stratégies de messagerie vocale hébergée

Une stratégie de messagerie vocale définit deux attributs que l’application de routage ExUM de Lync Server 2013 insère dans l’URI de requête d’un message d’invitation envoyé à l’implémentation de la messagerie unifiée Exchange hébergée :

  - **Destination :** Nom de domaine complet (FQDN) du service de messagerie unifiée Exchange hébergé. Cette valeur est utilisée par le serveur Edge Lync Server local à des fins de routage.
    
    <div>
    

    > [!NOTE]  
    > Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.

    
    </div>

  - **Organisation :** Nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé qui héberge les boîtes aux lettres de vos utilisateurs Lync Server 2013. Une stratégie de messagerie vocale peut contenir plusieurs organisations. Si plusieurs organisations sont incluses dans la stratégie, cet attribut doit être une liste séparée par des virgules des clients Exchange Server qui hébergent vos boîtes aux lettres utilisateur Lync Server 2013.

<div>


> [!NOTE]  
> L’administrateur client de votre service de messagerie unifiée Exchange hébergé fournit les valeurs nécessaires pour vos paramètres d’attribut de destination et d’organisation. Pour configurer votre stratégie, vous devez exécuter la cmdlet New-CsHostedVoicemailPolicy ou utiliser Set-CsHostedVoicemailPolicy pour modifier une stratégie existante (la stratégie globale, par exemple).



</div>

Pour plus d’informations sur la gestion des stratégies de messagerie vocale hébergée, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Attribution de stratégies de messagerie vocale par utilisateur

Si votre stratégie de messagerie vocale hébergée est définie avec une étendue par utilisateur, vous devez l’attribuer explicitement. Vous pouvez exécute la cmdlet Grant-CsHostedVoicemailPolicy pour attribuer la stratégie à des utilisateurs individuels ou des groupes.

Pour plus d’informations sur l’attribution ou la suppression d’une stratégie de messagerie vocale hébergée par utilisateur, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

