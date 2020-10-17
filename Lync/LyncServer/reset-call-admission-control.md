---
title: Réinitialisation du contrôle d’admission des appels
description: Réinitialiser le contrôle d’admission des appels.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4539cda453de6249be3a9b9b61521ecf478cb70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551240"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-11_

Si un pool frontal Lync Server 2010 héberge le contrôle d’admission des appels (CAC), vous devez déplacer le serveur de ports d’hébergement CAC vers un pool Lync Server 2013 avant de pouvoir supprimer le pool frontal Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Pour réinitialiser le service Contrôle d’admission des appels

1.  Ouvrez le Générateur de topologie.

2.  Cliquez avec le bouton droit sur le nœud du site, puis cliquez sur **Modifier les propriétés**.

3.  Sous **Définition du contrôle d’admission des appels**, assurez-vous que l’option **Activer le contrôle d’admission des appels** est sélectionnée.

4.  Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Lync Server 2013 qui doit héberger le contrôle d’admission des appels, puis cliquez sur **OK**.

5.  Publiez la topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

