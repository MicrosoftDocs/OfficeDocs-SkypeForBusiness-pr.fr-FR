---
title: 'Lync Server 2013 : installation des serveurs Edge'
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
ms.openlocfilehash: af95403b8a1fc383d8d6065f26a55242e735a51b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Installer des serveurs Edge pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Vous installez Lync Server 2013 sur des serveurs Edge à l’aide de l’Assistant Déploiement Lync Server. En exécutant l’Assistant Déploiement sur chaque serveur Edge, vous pouvez effectuer la plupart des tâches requises pour configurer le serveur Edge. Pour déployer Lync Server 2013 sur un serveur Edge, vous devez déjà exécuter le générateur de topologie pour définir et publier votre topologie de serveur Edge, puis l’exporter vers le média disponible à partir du serveur Edge. Pour plus d’informations, reportez-vous à la rubrique [scénarios pour l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) et [exportation de votre topologie Lync Server 2013 et copiez-la sur des médias externes pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Après avoir utilisé l’Assistant déploiement pour installer chaque serveur Edge, installer et affecter les certificats requis, et démarrer les services requis, vous pouvez effectuer l’installation en utilisant les informations de la procédure de configuration de la [prise en charge de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) pour activer et configurer l’accès des utilisateurs externes et les informations de [vérification de votre déploiement Edge dans 2013 Lync](lync-server-2013-verifying-your-edge-deployment.md)

<div>

## <a name="to-install-an-edge-server"></a>Pour installer un serveur Edge

1.  Ouvrez une session sur l’ordinateur sur lequel vous souhaitez installer le serveur Edge en tant que membre du groupe Administrateurs local ou avec un compte disposant de droits et d’autorisations équivalents.

2.  Assurez-vous que le fichier de configuration de topologie que vous avez créé à l’aide du générateur de topologie, puis exporté et copié vers le support externe, est disponible sur le serveur Edge (par exemple, l’accès au lecteur USB sur lequel vous avez copié le fichier de configuration de topologie, ou vérifiez accès au partage réseau où vous avez copié le fichier).

3.  Démarrez l’Assistant Déploiement.
    
    <div>
    

    > [!NOTE]  
    > Si vous obtenez un message vous indiquant que vous devez installer Microsoft Visual C++ Redistributable, cliquez sur <STRONG>Oui</STRONG>. Dans la boîte de dialogue suivante, acceptez l’<STRONG>emplacement d’installation</STRONG> par défaut ou cliquez sur <STRONG>Parcourir</STRONG> pour sélectionner un autre emplacement, puis cliquez sur <STRONG>Installer</STRONG>. Dans la boîte de dialogue suivante, activez la case à cocher <STRONG>J’accepte les termes du contrat de licence</STRONG>, puis cliquez sur <STRONG>OK</STRONG>.

    
    </div>

4.  Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.

5.  Une fois que l’Assistant a déterminé l’état du déploiement, pour **Étape 1. Installer le magasin de configurations local**, cliquez sur **Exécuter**, puis effectuez ce qui suit :
    
      - Dans la boîte de dialogue **Configurer le réplica local du magasin central de gestion**, cliquez sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**, accédez à l’emplacement du fichier de configuration de la topologie exporté, sélectionnez le fichier .zip, cliquez sur **Ouvrir**, puis sur **Suivant**.
    
      - L’Assistant Déploiement lit les informations de configuration du fichier de configuration et écrit le fichier de configuration XML sur l’ordinateur local.
    
      - Une fois que le processus **Exécution de commandes** est terminé, cliquez sur **Terminer**.

6.  Dans l’Assistant Déploiement, cliquez sur **étape 2 : installer ou supprimer des composants Lync Server** pour installer les composants de serveur Edge lync Server 2013 spécifiés dans le fichier de configuration XML qui est stocké sur l’ordinateur local.

7.  Une fois l’installation terminée, utilisez les informations de [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) pour installer et affecter les certificats requis avant de démarrer les services.

</div>

</div>

<span> </span>

</div>

</div>

</div>

