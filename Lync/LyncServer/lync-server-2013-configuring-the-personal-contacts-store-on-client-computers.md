---
title: 'Lync Server 2013: configuration du magasin de contacts personnels sur les ordinateurs clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4f9b7bbb50b5e63e87904d29a01715fcdcac8c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configuration du magasin de contacts personnels sur les ordinateurs clients pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-05_

Si vous intégrez Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, il est recommandé de configurer le magasin de contacts personnels sur les ordinateurs clients exécutant Microsoft Lync 2010. En particulier, vous devez configurer Lync pour qu’il utilise Exchange en tant que magasin de contacts personnel et, en même temps, veiller à ce que les utilisateurs ne puissent pas ignorer cette décision. Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.

Notez que cela n’est pas requis sur les ordinateurs exécutant Lync 2013.

Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :

1.  Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.

3.  Dans l’éditeur du Registre, développez l' **application** **HKEY\_local\_**, développez logiciel, développez **stratégies**, développez **Microsoft**, puis développez **Communicator**.

4.  Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.

5.  Une fois la nouvelle valeur créée, tapez **PersonalContactStoreOverride**, puis appuyez sur Entrée pour renommer la valeur.

6.  Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.

Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé. Pour plus d’informations, consultez la documentation relative [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)à la stratégie de groupe à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

