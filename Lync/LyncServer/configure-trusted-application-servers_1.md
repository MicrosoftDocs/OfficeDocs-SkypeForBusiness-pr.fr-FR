---
title: Configurer les serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb693a68f58ef16ca29048d9e18738ef98d719d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurer les serveurs d’applications approuvées

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées après avoir fusionné la topologie Office Communications Server héritée avec Lync Server 2013 et que vous définissez un nouveau serveur d’applications approuvées à l’aide du générateur de topologie, vous devez définir le pool de tronçon suivant comme étant un Pool Lync Server 2013. Dans un environnement fusionné, le pool Office Communications Server hérité et le pool Lync Server 2013 apparaissent dans la liste déroulante. La sélection du pool hérité *n’est pas* prise en charge.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Pour sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications approuvées

1.  Ouvrez une topologie existante dans le Générateur de topologie.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées**, puis cliquez sur **Nouveau pool d’applications approuvées**.

3.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée et indiquez s’il s’agit d’un déploiement d’un seul serveur ou de plusieurs serveurs.

4.  Cliquez sur **Suivant**.

5.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Lync Server 2013.
    
    ![Boîte de dialogue définir un nouveau pool d’applications approuvées](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Boîte de dialogue définir un nouveau pool d’applications approuvées")  

6.  Cliquez sur **Terminer**.

7.  Sélectionnez le nœud supérieur **Lync Server** puis, dans le volet **Actions**, sélectionnez **Publier**.

8.  Vérifiez si le **Pool d’applications approuvées** a été correctement créé et s’il est associé au pool frontal approprié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

