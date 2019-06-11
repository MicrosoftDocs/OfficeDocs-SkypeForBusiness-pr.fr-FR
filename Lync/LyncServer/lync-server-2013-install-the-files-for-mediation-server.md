---
title: 'Lync Server 2013: installer les fichiers pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Installer les fichiers pour le serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-08-06_

Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.

Suivez les étapes décrites dans cette rubrique pour exécuter l’Assistant Déploiement de Lync Server 2013 et installer les fichiers pour le serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation lorsque vous avez utilisé le générateur de topologie pour définir et publier le pool. Lors de l’installation de files Mediation Server, vous installez et attribuez également le certificat requis par chaque ordinateur d’un pool de serveurs de médiation.

Sur ce site, si vous avez déjà déployé des serveurs de médiation colocalisés sur les pools frontaux ou le serveur Standard Edition Server, vous pouvez ignorer cette rubrique et, à la place, continuer à [configurer les Trunks dans Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Cette rubrique part du principe que vous avez déjà défini et publié un pool de serveurs de médiation autonome comme décrit dans la rubrique <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">définir un serveur de médiation dans le générateur de topologie de Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publier la topologie dans Lync Server 2013</A> dans le déploiement. et que vous avez vérifié que les ordinateurs figurant dans le pool de serveurs de médiation répondent aux conditions préalables décrites dans la rubrique <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">logiciels requis pour Enterprise Voice dans Lync Server 2013</A> et la <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Configuration requise pour Voix entreprise dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Pour installer les fichiers sur un pool de serveurs de médiation autonome

1.  À partir du support d’installation, cliquez \<avec le\>bouton droit sur installation Media**\\Setup\\. exe amd64\\**, puis cliquez sur **exécuter en tant qu’administrateur**.

2.  Dans la page **Emplacement d’installation**, cliquez sur **OK**.

3.  Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)

4.  Dans la page **Assistant Déploiement de Lync Server 2010** , cliquez sur **installer ou mettre à jour le système de Lync Server**.

5.  Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.

6.  Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.

7.  Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.

8.  À côté de l' **étape 2: installer ou supprimer les composants Lync Server**, cliquez sur **exécuter**, puis sur **suivant**.

9.  Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.

10. Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.

11. Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.

12. Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.

13. Sur l’ordinateur sur lequel vous exécutez le panneau de configuration de Lync Server, vérifiez sur la page **Topology** du panneau de configuration de Lync Server que l’état du service du serveur de médiation est représenté par une coche verte. Si une croix rouge est affichée, sélectionnez le serveur de médiation. Dans le menu **Action**, cliquez sur **Démarrer tous les services**.

Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, suivez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveurs de médiation. Si vous n’avez pas besoin d’installer des fichiers pour un serveur de médiation pour d’autres ordinateurs, suivez les procédures décrites dans la section [configuration de Trunks dans Lync server 2013](lync-server-2013-configuring-trunks.md) pour configurer les paramètres de la connexion de Trunk entre ce pool de serveurs de médiation (ou toute la médiation Serveurs sur un site) et son homologue.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

