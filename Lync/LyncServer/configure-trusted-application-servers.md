---
title: Configurer les serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee36f365eeaf4d95dea824d8f3a3afa2544b1d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurer les serveurs d’applications approuvées

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-11_

Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool de tronçon suivant comme pool Lync Server 2013. Dans un environnement mixte, le pool Lync Server 2010 hérité et le pool Lync Server 2013 apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.

**Sélectionnez Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications approuvées**

1.  Ouvrez le Générateur de topologie.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées**, puis cliquez sur **Nouveau pool d’applications approuvées**.

3.  Entrez le **Nom de domaine complet du pool** de l’application approuvée et indiquez s’il s’agira d’un serveur unique ou d’un serveur multiple.

4.  Cliquez sur **Suivant**.

5.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Lync Server 2013.

6.  Cliquez sur **Terminer**.

7.  Sélectionnez le nœud supérieur **Lync Server** et dans le menu **Action**, sélectionnez **Publier**.
    
    Le **Pool d’applications approuvées** doit avoir été créé avec succès et être associé au pool frontal correct.

</div>

<span> </span>

</div>

</div>

</div>

