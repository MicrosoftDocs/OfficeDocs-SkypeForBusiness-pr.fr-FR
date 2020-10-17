---
title: 'Lync Server 2013 : présentation de l’ID de l’appelant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24ca692dcfa4b2281fcb324c0f5fef5584b5a24e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508161"
---
# <a name="caller-id-presentation-in-lync-server-2013"></a>Présentation de l’ID de l’appelant dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Avec Lync Server 2010, le numéro de téléphone de la partie appelée (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par l’homologue de jonction (c’est-à-dire, la passerelle associée, le PBX (Private Branch Exchange) ou la jonction SIP). Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.

Lync Server 2013 offre la possibilité de traduire également le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone à partir duquel l’appelant est appelé) du format E. 164 au format de numérotation local requis par l’homologue de jonction. Par exemple, vous pouvez écrire une règle de traduction pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

<div id="sectionSection0" class="section">

**Pour configurer l’ID de l’appelant à l’aide du panneau de configuration Lync Server**

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

5.  Pour configurer la présentation de l’identification de l’appelant :
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Règles de traduction du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.
    
    <div>
    

    > [!WARNING]  
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

