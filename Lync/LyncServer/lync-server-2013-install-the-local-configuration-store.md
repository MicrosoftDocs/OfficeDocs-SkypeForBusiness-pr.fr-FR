---
title: 'Lync Server 2013 : Installation du magasin de configurations local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Installation du magasin de configurations local dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-27_

Avant de procéder à ces étapes, assurez-vous que vous êtes connecté au serveur à l’aide d’un compte d’utilisateur de domaine qui est un administrateur local et un membre du groupe RTCUniversalReadOnlyAdmin.

Pour pouvoir utiliser l’Assistant Déploiement de Lync Server, le magasin de configuration local doit exister sur un serveur. Le magasin de configuration local est une copie en lecture seule du magasin de gestion central, qui est créée après l’installation locale de SQL Server Express. Le magasin de gestion central proprement dit est ajouté à la base de données SQL Server existante qui est installé sur la base de données SQL Server Standard Server ou SQL Server Express.

<div>


> [!IMPORTANT]  
> Si vous n’avez pas encore exécuté le programme d’installation de Lync Server 2013 sur ce serveur, vous serez invité à entrer un lecteur et un chemin d’accès pour installer Lync Server 2013. Cela vous permettra de procéder à l’installation sur un lecteur autre que le lecteur système, si votre organisation l’exige, ou si vous avez des problèmes d’espace. Dans la boîte de dialogue d’installation, il vous suffit de changer le chemin d’accès d’installation pour les fichiers du serveur Lync vers un nouveau lecteur disponible. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Lync Server 2013 y sera également déployé.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Pour installer le magasin de configuration local

1.  À partir de votre support d’installation \\,\\accédez\\à Setup. exe. exe, puis cliquez sur **OK**.

2.  Si vous êtes invité à installer Microsoft Visual C++ 2012 redistribuable, cliquez sur **Oui**.

3.  Dans la page de l’emplacement de l' **installation de Lync Server 2013** , cliquez sur **OK**.

4.  Sur la page **contrat de licence utilisateur final** , passez en revue les termes du contrat de licence, vous devez sélectionner **J’accepte les conditions du contrat de licence**, puis cliquez sur **OK** pour pouvoir continuer.

5.  Dans la page de l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système serveur Lync**.

6.  Sur la page **Lync Server 2013** , à côté de la page **étape suivante: installer le magasin de configuration local**, cliquez sur **exécuter**.

7.  Dans la page **Installer le magasin de configurations local**, assurez-vous que l’option **Récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.

8.  Lorsque l’installation de configuration du serveur local est terminée, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

