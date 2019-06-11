---
title: Configuration des serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a27dbab3e954c96a07739f8a214ae7d1ec87ace
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configuration des serveurs d’applications approuvées

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-11_

Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance, vous devez définir le pool de sauts suivant comme pool Lync Server 2013. Dans un environnement mixte, le pool Lync Server 2010 hérité et le pool 2013 du serveur Lync apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.

**Sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications de confiance**

1.  Ouvrez le générateur de topologie.

2.  Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance** , puis cliquez sur **nouveau pool d’applications de confiance**.

3.  Entrez le **nom de domaine complet (FQDN)** du pool d’applications de confiance et sélectionnez s’il s’agit d’un serveur unique ou d’un serveur multiple.

4.  Cliquez sur **Suivant**.

5.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal de Lync Server 2013.

6.  Cliquez sur **Terminer**.

7.  Sélectionnez le nœud supérieur **serveur Lync** et dans le menu **action** , sélectionnez **publier**.
    
    Vérifiez que le **pool d’applications approuvé** a été créé avec succès et est associé au pool frontal approprié.

</div>

<span> </span>

</div>

</div>

</div>

