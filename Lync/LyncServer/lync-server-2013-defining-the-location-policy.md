---
title: 'Lync Server 2013: définition de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Définition de la stratégie d’emplacement pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-29_

Chaque stratégie d’emplacement renferme les informations suivantes :

  - **Services d’urgence activés**  
    Lorsque cette valeur est **Oui**, le client est activé pour E9-1-1. Lors de l’inscription d’un client, ce dernier tente d’acquérir un emplacement auprès du service d’information d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.

<!-- end list -->

  - **Emplacement requis**  
    Ce paramètre est utilisé uniquement lorsque l’option **services d’urgence** est définie sur **Oui**.
    
    Vous pouvez configurer le paramètre de l' **emplacement requis** pour définir le comportement du client. Si vous sélectionnez **Non **, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous sélectionnez **Oui **, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous sélectionnez **Clause d’exclusion de responsabilité **, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite. Dans tous les cas, l'utilisateur peut continuer d'utiliser le client.
    
    <div>
    

    > [!NOTE]  
    > Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité. 

    
    </div>

<!-- end list -->

  - **Clause d’exclusion de responsabilité du service d’urgence**  
    Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement. Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différentes exclusions de responsabilité pour différents paramètres régionaux ou ensembles d’utilisateurs différents.
    
    <div>
    

    > [!NOTE]  
    > Ce paramètre de stratégie d’emplacement est différent de celui de Lync Server 2010, à partir duquel vous avez utilisé l’applet de passe <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> pour définir une exclusion de responsabilité globale pour l’ensemble de l’organisation. S’il existe déjà une clause d’exclusion de responsabilité globale, vous devez spécifier ce démenti dans la stratégie d’emplacement. Autrement dit, Lync Server 2013 utilise uniquement les exclusions de responsabilité spécifiées dans la stratégie d’emplacement.

    
    </div>

<!-- end list -->

  - **Chaîne de numérotation d’urgence**  
    Cette chaîne de numérotation (moins le "+" au début, mais y compris la normalisation réalisée par le plan de numérotation de l’utilisateur Lync) signifie qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.
    
    <div>
    

    > [!NOTE]  
    > Si votre organisation n’utilise pas un préfixe d’accès aux lignes externes, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute «+» à la chaîne 911 avant d’envoyer l’appel vers le routage sortant sur un serveur de pool Lync. le "+" sera automatiquement ajouté par le client Lync en raison de la stratégie d’emplacement. Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation appropriée qui élimine le préfixe d’accès externe et ajoute le signe «+». Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur&nbsp;compose 9 911 pour passer un appel d’urgence, le client utilise sa stratégie de plan de numérotation pour normaliser cette opération sur + 911 avant que le numéro composé soit évalué par les itinéraires dans l’emplacement de l’appelant. tournage.

    
    </div>

<!-- end list -->

  - **Masques de chaînes de numérotation d’urgence**  
    Liste séparée par des virgules des chaînes de numérotation traduites dans la chaîne de numérotation de **secours**spécifiée. Par exemple, vous souhaiterez peut-être ajouter 112, qui est le numéro de service d’urgence pour la plupart des services d’Europe. Un utilisateur de Lync à partir de l’Europe peut ne pas savoir que 911 est le numéro d’urgence des États-Unis et peut 112 composer le même résultat. Comme pour la chaîne de numérotation d’urgence, n’incluez pas de "+" devant chaque numéro et, si vous utilisez des codes d’accès de ligne externe, assurez-vous que la stratégie de plan de numérotation de l’utilisateur dispose de règles de normalisation pour supprimer le code d’accès.

<!-- end list -->

  - **Utilisation PSTN**  
    Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels seront acheminés.
    
    <div>
    

    > [!NOTE]  
    > Seule une utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation PSTN remplace les utilisations PSTN affectées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passés à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence.

    
    </div>

<!-- end list -->

  - **URI de notification**  
    Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.

<!-- end list -->

  - **URI de la conférence**  
    Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.  

<!-- end list -->

  - **Mode Conférence**  
    Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle. 

<!-- end list -->

  - **Intervalle d’actualisation d’emplacement**  
    Spécifie la durée (en heures) entre les demandes des clients pour une mise à jour de l’emplacement du service d’informations d’emplacement. La valeur peut être comprise entre 1 et 12. La valeur par défaut est 4.

</div>

<span> </span>

</div>

</div>

</div>

