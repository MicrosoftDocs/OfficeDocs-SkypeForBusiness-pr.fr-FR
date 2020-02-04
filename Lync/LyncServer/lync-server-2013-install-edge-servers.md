---
title: 'Lync Server 2013 : Installation des serveurs Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d1961a158ead735ae63d20bb2bd233d6ed5958
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Installation des serveurs Edge pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Vous installez Lync Server 2013 sur les serveurs Edge à l’aide de l’Assistant Déploiement de Lync Server. En exécutant l’Assistant Déploiement sur chaque serveur Edge, vous pouvez effectuer la plupart des tâches nécessaires à la configuration du serveur Edge. Pour déployer Lync Server 2013 sur un serveur Edge, vous devez avoir déjà exécuté le générateur de topologie pour définir et publier votre topologie de serveur Edge, puis l’exporter vers un fichier multimédia disponible sur le serveur Edge. Pour plus d’informations, reportez-vous à la rubrique [scénarios d’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) et [exporter votre topologie Lync Server 2013 et les copier sur des éléments multimédias externes pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Après avoir utilisé l’Assistant déploiement pour installer chaque serveur Edge, installez et attribuez les certificats requis, et démarrez les services requis, vous pouvez terminer la configuration en utilisant les informations de configuration de la [prise en charge de l’accès des utilisateurs externes 2013 dans](lync-server-2013-configuring-support-for-external-user-access.md) lync Server 2013 afin d’activer et de configurer l’accès des utilisateurs externes et les informations dans la [vérification de votre déploiement Edge dans Lync Server](lync-server-2013-verifying-your-edge-deployment.md) .

<div>

## <a name="to-install-an-edge-server"></a>Pour installer un serveur Edge

1.  Ouvrez une session sur l’ordinateur sur lequel vous voulez installer votre serveur Edge en tant que membre du groupe d’administrateurs local ou d’un compte disposant de droits d’utilisateur et d’autorisations équivalentes.

2.  Assurez-vous que le fichier de configuration de la topologie que vous avez créé à l’aide du générateur de topologie, puis exporté et copié sur le média externe est disponible sur le serveur Edge (par exemple, accès au lecteur USB sur lequel vous avez copié le fichier de configuration de la topologie, ou vérifier accès au partage réseau sur lequel vous avez copié le fichier).

3.  Démarrez l’Assistant déploiement.
    
    <div>
    

    > [!NOTE]  
    > Si un message s’affiche indiquant que vous devez installer Microsoft Visual C++ redistribuable, cliquez sur <STRONG>Oui</STRONG>. Dans la boîte de dialogue suivante, vous pouvez accepter l' <STRONG>emplacement d’installation</STRONG> par défaut ou cliquer sur <STRONG>Parcourir</STRONG> pour sélectionner un autre emplacement, puis cliquer sur <STRONG>installer</STRONG>. Dans la boîte de dialogue suivante, activez la case à cocher <STRONG>J’accepte les termes du contrat de licence</STRONG> , puis cliquez sur <STRONG>OK</STRONG>.

    
    </div>

4.  Dans l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système serveur Lync**.

5.  Après que l’Assistant a déterminé l’état de déploiement, pour l' **étape 1. Installez le magasin de configurations local**, cliquez sur **exécuter** , puis procédez comme suit :
    
      - Dans la boîte de dialogue **configurer le réplica local du magasin central de gestion** , cliquez sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**, accédez à l’emplacement du fichier de configuration topologique exporté, sélectionnez le fichier. zip, cliquez sur **ouvrir**, puis sur **suivant**.
    
      - L’Assistant Déploiement lit les informations de configuration du fichier de configuration et enregistre le fichier de configuration XML sur l’ordinateur local.
    
      - Une fois que la procédure **Exécution de commandes** est terminé, cliquez sur **Terminer**.

6.  Dans l’Assistant Déploiement, cliquez sur **étape 2 : installer ou supprimer les composants Lync Server** pour installer les composants Edge de lync Server 2013 spécifiés dans le fichier de configuration XML stocké sur l’ordinateur local.

7.  À l’issue de l’installation, utilisez les informations de la rubrique [configurer des certificats d’affichage pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) afin d’installer et d’affecter les certificats requis avant de démarrer les services.

</div>

</div>

<span> </span>

</div>

</div>

</div>

