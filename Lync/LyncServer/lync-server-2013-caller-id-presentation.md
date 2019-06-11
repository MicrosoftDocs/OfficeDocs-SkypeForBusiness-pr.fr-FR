---
title: 'Lync Server 2013: présentation ID de l’appelant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016913ad68865f7d93512cc7383f2cfb47497ebe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Présentation de l’identification de l’appelant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Avec Lync Server 2010, le numéro de téléphone de la personne appelé (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par le Trunk pair (c’est-à-dire, la passerelle associée, le PBX (PBX) ou le Trunk SIP). À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.

Lync Server 2013 introduit une option permettant de traduire également le numéro de téléphone de la personne qui appelle (c’est-à-dire, le numéro de téléphone à partir duquel l’appelant appelle) le format E. 164 au format de numérotation local requis par l’homologue de Trunk. Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

<div id="sectionSection0" class="section">

**Pour configurer l’identification de l’appelant à l’aide du panneau de configuration de Lync Server**

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

5.  Pour configurer la présentation de l’identification de l’appelant :
    
      - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Règles de conversion du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

