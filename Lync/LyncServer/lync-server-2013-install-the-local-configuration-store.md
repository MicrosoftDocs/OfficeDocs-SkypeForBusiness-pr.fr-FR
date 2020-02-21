---
title: 'Lync Server 2013 : installation du magasin de configurations local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c95399aa7cccf28ec0c236c2882b6f44794e80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Installer le magasin de configurations local dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-27_

Avant de suivre ces étapes, vérifiez que vous êtes connecté au serveur avec un compte d’utilisateur de domaine qui est à la fois un administrateur local et un membre du groupe RTCUniversalReadOnlyAdmin.

Pour pouvoir faire quoi que ce soit avec l’Assistant Déploiement Lync Server, nous avons besoin que le magasin de configuration local existe sur un serveur. Le magasin de configurations local est une copie en lecture seule du magasin central de gestion, qui est créée après l’installation locale de SQL Server Express. Le magasin central de gestion lui-même est ajouté à la base de données SQL Server existante installée sur le serveur Standard Edition ou la base de données SQL Server Express.

<div>


> [!IMPORTANT]  
> Si vous n’avez pas encore exécuté le programme d’installation de Lync Server 2013 sur ce serveur, vous serez invité à indiquer un lecteur et un chemin d’accès pour installer Lync Server 2013. Cela vous permettra d’effectuer l’installation sur un lecteur autre que le lecteur système, si votre organisation l’exige ou si vous avez des préoccupations en matière d’espace. Vous pouvez simplement modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue d’installation avec un nouveau lecteur disponible. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Lync Server 2013 se déploiera également.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Pour installer le magasin de configurations local

1.  À partir de votre support d’installation \\,\\naviguez jusqu’à Setup amd64\\Setup. exe, puis cliquez sur **OK**.

2.  Si vous êtes invité à installer Microsoft Visual C++ 2012 Redistributable, cliquez sur **Oui**.

3.  Sur la page **emplacement d’installation de Lync Server 2013** , cliquez sur **OK**.

4.  Dans la page **contrat de licence utilisateur final** , lisez les termes du contrat de licence, vous devez sélectionner **J’accepte les termes du contrat de licence**, puis cliquer sur **OK** pour pouvoir continuer.

5.  Sur la page Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.

6.  Sur la page **Lync Server 2013** , en regard de **étape 1 : installer le magasin de configurations local**, cliquez sur **exécuter**.

7.  Sur la page **installer le magasin de configurations local** , assurez-vous que l’option **récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **suivant**.

8.  Une fois l’installation de la configuration du serveur local terminée, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

