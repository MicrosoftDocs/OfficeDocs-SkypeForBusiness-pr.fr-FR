---
title: 'Lync Server 2013 : configuration du magasin de contacts personnels sur les ordinateurs clients'
description: 'Lync Server 2013 : configuration du magasin de contacts personnels sur les ordinateurs clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1040b3eb9aa38e3e0c537d690b9292ab8f1ead2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544190"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configuration du magasin de contacts personnels sur les ordinateurs clients pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Si vous intégrez Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, il est recommandé de configurer le magasin de contacts personnels sur les ordinateurs clients exécutant Microsoft Lync 2010. En particulier, vous devez configurer Lync pour qu’il utilise Exchange comme magasin de contacts personnel et, en même temps, vérifier que les utilisateurs ne sont pas en mesure de remplacer cette décision. Cette opération peut être réalisée en créant et en configurant une valeur de Registre sur chaque ordinateur client.

Notez que cette fonction n’est pas obligatoire sur les ordinateurs exécutant Lync 2013.

Pour configurer cette valeur sur un seul ordinateur, procédez comme suit :

1.  Sur l’ordinateur client, cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez regedit, puis appuyez sur Entrée.

3.  Dans l’éditeur du Registre, développez **HKEY \_ local \_ machine**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.

4.  Cliquez avec le bouton droit sur **Communicator**, pointez sur **nouveau**, puis cliquez sur **valeur DWORD (32 bits)**.

5.  Une fois la nouvelle valeur créée, tapez **PersonalContactStoreOverride** , puis appuyez sur entrée pour renommer la valeur.

6.  Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’éditeur du Registre.

Si vous devez effectuer cette même modification sur plusieurs ordinateurs, vous pouvez le faire en créant un objet de stratégie de groupe personnalisé. Pour plus d’informations, consultez la documentation sur la stratégie de groupe à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .

</div>

<span> </span>

</div>

</div>

</div>

