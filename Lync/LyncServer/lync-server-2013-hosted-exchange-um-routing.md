---
title: 'Lync Server 2013 : routage de messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57efdcebe52f9b32f30c22ebcbf107d3cd9d8a7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Routage de messagerie unifiée Exchange hébergée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

L’application de routage de messagerie unifiée Exchange s’exécute sur le serveur frontal pour acheminer les appels, soit vers un déploiement de messagerie unifiée Microsoft Exchange Server local, soit vers un service de messagerie UNIFIÉe Exchange hébergé.

<div>

## <a name="the-exum-routing-application"></a>Application de routage ExUM

L’application de routage de messagerie unifiée Exchange Lync Server 2013 utilise les informations des paramètres de compte d’utilisateur et de stratégie de messagerie vocale hébergée pour déterminer comment acheminer les appels pour la messagerie vocale hébergée, comme illustré dans le diagramme suivant.

**Exemple de routage sur un déploiement de messagerie unifiée Exchange mixte**

![Déploiement de la messagerie unifiée Lync Server Exchange sur site](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Déploiement de la messagerie unifiée Lync Server Exchange sur site")

Le routage de messagerie unifiée Exchange peut être configuré pour acheminer les appels aux utilisateurs qui sont activés pour la messagerie unifiée Exchange locale, aux utilisateurs qui sont activés pour la messagerie unifiée Exchange hébergée ou à une combinaison des deux.

Par exemple, supposons que la boîte aux lettres de Roy et le service de messagerie unifiée Exchange sont hébergés dans un déploiement Exchange local.

  - Les informations d’adresse proxy du compte d’utilisateur de Roy fournissent les informations utilisées par l’application de routage ExUM pour acheminer ses appels vers un serveur de messagerie unifiée Exchange local.

La boîte aux lettres d’Alice et le service de messagerie unifiée Exchange se trouvent dans le centre de données d’un fournisseur de services Exchange hébergé. Le routage des appels de messagerie unifiée Exchange est configuré comme suit :

  - Les valeurs définies dans l’attribut msExchUCVoiceMailSettings du compte utilisateur d’Alice indiquent à l’application de routage ExUM de contrôler les informations de routage dans une stratégie de messagerie vocale hébergée.
    
    <div>
    

    > [!NOTE]  
    > La valeur de l’attribut msExchUCVoiceMailSettings peut être définie par le fournisseur de services Exchange ou par l’administrateur Lync Server 2013. Dans l’exemple illustré dans le diagramme précédent, la valeur (CsHostedVoiceMail = 1) a été définie par l’administrateur Lync Server 2013 pour activer la messagerie vocale hébergée pour Alice. Pour plus d’informations sur cet attribut, consultez la rubrique <A href="lync-server-2013-hosted-exchange-user-management.md">gestion des utilisateurs Exchange hébergés dans Lync Server 2013</A>.

    
    </div>

  - La stratégie de messagerie vocale hébergée attribuée au compte utilisateur d’Alice fournit les détails de routage suivants :
    
      - La destination est le fournisseur de services de messagerie unifiée Exchange hébergé (LS. ExUm. \<hostedExchangeServer\>. com dans cet exemple).
    
      - Les organisations sont identifiées par les ID de client, qui sont les noms de domaine complets de routage pour les messages SIP pour les clients Exchange Server qui se trouvent sur ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com et Corp.litwareinc.com dans cet exemple).
        
        <div>
        

        > [!NOTE]  
        > Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.

        
        </div>
        
        Pour plus d’informations, reportez-vous à [stratégies de messagerie vocale hébergée dans Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Si les paramètres d’attribut msExchUCVoiceMailSettings et d’adresse proxy de messagerie unifiée sont tous deux présents dans un compte d’utilisateur, l’attribut msExchUCVoiceMailSettings est prioritaire.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

