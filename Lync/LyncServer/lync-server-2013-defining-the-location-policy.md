---
title: 'Lync Server 2013 : définition de la stratégie d’emplacement'
description: 'Lync Server 2013 : définition de la stratégie d’emplacement.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddd5b2ce34e44240162e886672a236789857e7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567536"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a>Définition de la stratégie d’emplacement pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Chaque stratégie d’emplacement contient les informations suivantes :

  - **Services d’urgence activés**  
    Si cette valeur est **Oui**, le client est activé pour E9-1-1. Lorsqu’un client s’inscrit, il tente d’acquérir un emplacement à partir du service d’informations d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.

<!-- end list -->

  - **Emplacement requis**  
    Ce paramètre est utilisé uniquement lorsque l’option **services d’urgence activé**   est définie sur **Oui**.
    
    Vous pouvez configurer le paramètre **emplacement requis** pour définir le comportement du client. La définition de la valeur sur **non** signifie que l’utilisateur ne sera pas invité à entrer un emplacement. La définition de la valeur sur **Oui** signifie que l’utilisateur sera invité à entrer un emplacement, mais peut ignorer l’invite. Si la valeur est définie sur **clause d’exclusion de responsabilité** , l’utilisateur sera invité à entrer un emplacement et une clause d’exclusion de responsabilité s’affichera si les utilisateurs essaient de le faire. Dans tous les cas, l’utilisateur peut continuer à utiliser le client.
    
    <div>
    

    > [!NOTE]  
    > Le texte de la clause d’exclusion de responsabilité n’apparaît pas si un utilisateur a entré manuellement un emplacement avant d’être activé pour E9-1-1. Les mises à jour du texte de la clause d’exclusion de responsabilité ne seront pas visibles par les utilisateurs qui ont déjà consulté la clause d’exclusion de responsabilité.

    
    </div>

<!-- end list -->

  - **Clause d’exclusion de responsabilité de service d’urgence améliorée**  
    Ce paramètre spécifie la clause d’exclusion de responsabilité que les utilisateurs voient si l’invite pour un emplacement est rejetée. Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différents clauses d’exclusion de responsabilité pour différents paramètres régionaux ou groupes d’utilisateurs.
    
    <div>
    

    > [!NOTE]  
    > Ce paramètre de stratégie d’emplacement diffère de Lync Server 2010, où vous avez utilisé l’applet de commande <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> pour définir une clause d’exclusion de responsabilité globale pour l’ensemble de l’organisation. S’il existe déjà une clause d’exclusion de responsabilité globale, vous devez spécifier cette clause d’exclusion de responsabilité dans la stratégie d’emplacement. En d’autres conditions, Lync Server 2013 utilise uniquement les clauses d’exclusion de responsabilité spécifiées dans la stratégie d’emplacement.

    
    </div>

<!-- end list -->

  - **Chaîne de numérotation d’urgence**  
    Cette chaîne de numérotation (moins le « + » de début, mais y compris toute normalisation réalisée par le plan de numérotation de l’utilisateur Lync) signifie qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** oblige le client à inclure des informations d’emplacement et de rappel avec l’appel.
    
    <div>
    

    > [!NOTE]  
    > Si votre organisation n’utilise pas de préfixe d’accès à une ligne externe, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute le signe « + » à la chaîne 911 avant l’envoi de l’appel vers le routage sortant sur un serveur de pool Lync ; le signe « + » sera automatiquement ajouté par le client Lync à la suite de la stratégie d’emplacement. Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation applicable qui supprime le préfixe d’accès externe et ajoute le signe « + ». Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur compose le &nbsp; numéro 9 911 pour passer un appel d’urgence, le client utilise sa stratégie de plan de numérotation pour normaliser cette opération à + 911 avant que le numéro composé soit évalué par les itinéraires dans le profil d’emplacement de l’appelant.

    
    </div>

<!-- end list -->

  - **Masques de chaîne de numérotation d’urgence**  
    Liste de chaînes de numérotation séparées par des points-virgules qui est traduite dans la **chaîne de numérotation d’urgence**spécifiée. Par exemple, vous pouvez ajouter 112, qui est le numéro de service d’urgence pour la plupart d’Europe. Un utilisateur de Lync visitant l’Europe peut ne pas savoir que 911 est le numéro de secours américain, mais il peut composer 112 et obtenir le même résultat. Comme pour la chaîne de numérotation d’urgence, n’incluez pas de signe « + » devant chaque numéro, et si vous utilisez des codes d’accès aux lignes externes, assurez-vous que les règles de normalisation dans la stratégie de plan de numérotation de l’utilisateur suppriment le chiffre de code d’accès.

<!-- end list -->

  - **Utilisation PSTN**  
    Le nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou les appels d’urgence de passerelle ELIN vers.
    
    <div>
    

    > [!NOTE]  
    > Une seule utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation PSTN remplace les utilisations PSTN attribuées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passés à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence.

    
    </div>

<!-- end list -->

  - **URI de notification**  
    Spécifie un ou plusieurs URI SIP du personnel de sécurité qui reçoit une notification de messagerie instantanée lors de la mise en place d’un appel d’urgence. Les groupes de distribution sont pris en charge.

<!-- end list -->

  - **URI de la conférence**  
    Spécifie un numéro de numérotation directe vers l’intérieur (en général, un numéro de service de sécurité) qui doit être mis en conférence en cas d’appel d’urgence.

<!-- end list -->

  - **Mode conférence**  
    Indique si l’URI de la Conférence doit être mis en conférence dans l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle.

<!-- end list -->

  - **Intervalle d’actualisation de l’emplacement**  
    Spécifie la durée (en heures) entre les demandes client pour une mise à jour d’emplacement à partir du service d’informations d’emplacement. La valeur peut être définie sur n’importe quelle valeur comprise entre 1 et 12. La valeur par défaut est 4.

</div>

<span> </span>

</div>

</div>

</div>

