---
title: Configuration des serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60aef8ea63d4feb0e874f72d37670c3b06860758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configuration des serveurs d’applications approuvées

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance après la fusion de la topologie Office Communications Server héritée avec Lync Server 2013 et que vous définissez un nouveau serveur d’applications de confiance à l’aide du générateur de topologie, vous devez définir le pool de sauts suivant comme étant Pool Lync Server 2013. Dans un environnement fusionné, le pool Office Communications Server hérité et le pool Lync Server 2013 apparaissent dans la liste déroulante. La sélection du pool hérité n’est *pas* prise en charge.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Pour sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications de confiance

1.  Ouvrez une topologie existante dans le générateur de topologie.

2.  Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance** , puis cliquez sur **nouveau pool d’applications de confiance**.

3.  Entrez le **nom de domaine complet (FQDN)** du pool d’applications de confiance et sélectionnez s’il s’agit d’un déploiement sur un serveur ou sur plusieurs serveurs.

4.  Cliquez sur **Suivant**.

5.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal de Lync Server 2013.
    
    ![Boîte de dialogue définir un nouveau pool d’applications de confiance] (images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Boîte de dialogue définir un nouveau pool d’applications de confiance")  

6.  Cliquez sur **Terminer**.

7.  Sélectionnez le nœud supérieur **serveur Lync** , puis, dans le volet **actions** , sélectionnez **publier**.

8.  Vérifiez que le **pool d’applications approuvé** a été correctement créé et qu’il est associé au pool frontal approprié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

