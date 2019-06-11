---
title: 'Lync Server 2013 : Routage de la messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Routage de la messagerie unifiée Exchange hébergée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

L’application de routage de messagerie unifiée Exchange s’exécute sur le serveur frontal pour acheminer les appels vers un déploiement local de messagerie unifiée (MU) sur site ou vers un service de messagerie UNIFIÉe Exchange hébergé.

<div>

## <a name="the-exum-routing-application"></a>Application de routage ExUM

L’application de routage de messagerie unifiée Exchange Server 2013 utilise les informations des paramètres de compte d’utilisateur et les paramètres de stratégie de messagerie vocale hébergés pour déterminer le mode de routage des appels pour la boîte vocale hébergée, comme indiqué dans le schéma suivant.

**Exemple de routage de MU Exchange de déploiement mixte**

![Déploiement de la messagerie unifiée Exchange Server en local] (images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Déploiement de la messagerie unifiée Exchange Server en local")

Le routage de MU Exchange peut être configuré pour diriger les appels vers les utilisateurs qui sont activés pour la messagerie unifiée Exchange locale, pour les utilisateurs qui sont activés pour la messagerie unifiée Exchange hébergée ou pour une combinaison des deux.

Par exemple, supposons que la boîte aux lettres de Roy et le service de messagerie unifiée Exchange résident dans un déploiement Exchange local.

  - Les informations d’adresse proxy du compte utilisateur de Roy fournissent les informations utilisées par l’application de routage ExUM pour diriger ses appels vers un serveur Exchange UM local.

Les services de boîte aux lettres et de messagerie unifiée d’Alice sont situés dans le centre de données du fournisseur de services Exchange hébergé. Le routage des appels de messagerie unifiée Exchange est configuré comme suit:

  - Les valeurs définies dans l’attribut msExchUCVoiceMailSettings du compte d’utilisateur d’Alice indiquent à l’application de routage ExUM de vérifier les détails de routage dans une stratégie de messagerie vocale hébergée.
    
    <div>
    

    > [!NOTE]  
    > La valeur de l’attribut msExchUCVoiceMailSettings peut être définie par le fournisseur de services Exchange ou par l’administrateur 2013 de Lync Server. Dans l’exemple ci-dessus, la valeur (CsHostedVoiceMail = 1) a été définie par l’administrateur de Lync Server 2013 pour activer la messagerie vocale hébergée pour Alice. Pour plus d’informations sur cet attribut, voir <A href="lync-server-2013-hosted-exchange-user-management.md">gestion des utilisateurs Exchange hébergés dans Lync Server 2013</A>.

    
    </div>

  - La stratégie de messagerie vocale hébergée qui est affectée au compte d’utilisateur d’Alice fournit des informations de routage:
    
      - La destination est le fournisseur de service de messagerie unifiée Exchange hébergé (LS. ExUm. \<hostedExchangeServer\>. com dans cet exemple).
    
      - Les organisations sont identifiées par les ID de locataire, qui sont les noms de domaine complets de routage pour les messages SIP pour les clients Exchange Server situés sur ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com et Corp.litwareinc.com dans cet exemple).
        
        <div>
        

        > [!NOTE]  
        > Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.

        
        </div>
        
        Pour plus d’informations, reportez-vous [à stratégies de messagerie vocale hébergées dans Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Si l’attribut msExchUCVoiceMailSettings et les paramètres d’adresse proxy de messagerie unifiée sont tous deux présents dans un compte d’utilisateur, l’attribut msExchUCVoiceMailSettings est prioritaire.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

