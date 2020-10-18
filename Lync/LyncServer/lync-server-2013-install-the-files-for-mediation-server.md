---
title: 'Lync Server 2013 : installation des fichiers pour le serveur de médiation'
description: 'Lync Server 2013 : Installez les fichiers pour le serveur de médiation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574070"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Installer les fichiers pour le serveur de médiation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-06_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine qui est membre du groupe RTCUniversalReadOnlyAdmins au moins.

Suivez les étapes décrites dans cette rubrique pour exécuter l’Assistant Déploiement de Lync Server 2013 afin d’installer les fichiers du serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation lorsque vous avez utilisé le générateur de topologies pour définir et publier le pool. Lors de l’installation du serveur de médiation des fichiers, vous installez et attribuez également le certificat requis par chaque ordinateur dans un pool de serveurs de médiation.

Sur ce site, si vous avez déjà déployé des serveurs de médiation colocalisés sur les pools frontaux ou le serveur Standard Edition, vous pouvez ignorer cette rubrique et, au lieu de cela, poursuivre la [Configuration des jonctions dans Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Cette rubrique suppose que vous ayez déjà défini et publié un pool de serveurs de médiation autonome tel que décrit dans <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">define a Mediation Server in Topology Builder in Lync Server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> dans la documentation de déploiement. et que vous ayez vérifié que les ordinateurs du pool de serveurs de médiation répondent aux exigences décrites dans <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Prerequisites for enterprise Voice in Lync Server 2013</A> , <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Pour installer les fichiers pour un pool de serveurs de médiation autonome

1.  À partir du support d’installation, cliquez avec le bouton droit sur \<installation media\> ** \\ Setup \\ amd64 \\Setup.exe**, puis cliquez sur **exécuter en tant qu’administrateur**.

2.  Sur la page **emplacement d’installation** , cliquez sur **OK**.

3.  Dans la page **contrat de licence utilisateur final** , cliquez sur **J’accepte**, puis sur **OK**. (Requis pour continuer)

4.  Sur la page **Assistant Déploiement de Lync server 2010** , cliquez sur **installer ou mettre à jour le système Lync Server**.

5.  En regard de **étape 1 : installer le magasin de configurations local**, cliquez sur **exécuter**, puis suivez les instructions affichées à l’écran.

6.  Sur la page **configurer le réplica local du magasin central de gestion** , acceptez l’extraction par défaut **directement à partir du magasin central de gestion**, puis cliquez sur **suivant**.

7.  Sur la page **exécution de commandes** , lorsque l’état de la tâche est **terminé**, cliquez sur **Terminer**.

8.  En regard de **étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **exécuter**, puis sur **suivant**.

9.  Sur la page **exécution de commandes** , lorsque l’état de la tâche est **terminé**, cliquez sur **Terminer**.

10. En regard de l' **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat, et vous exécuterez l' **étape 3** deux fois : une fois pour émettre le certificat requis, et une fois encore plus pour l’attribuer.

11. Une fois que le certificat a été émis et affecté correctement, à l' **étape 4 : démarrer les services**, cliquez sur **exécuter**, puis suivez les instructions à l’écran.

12. Lorsque l' **étape 4** s’est correctement déroulée, redémarrez le serveur et connectez-vous au serveur en tant que membre du groupe Admins du serveur.

13. Sur l’ordinateur sur lequel vous exécutez le panneau de configuration Lync Server, vérifiez sur la page **topologie** du panneau de configuration Lync Server que l’état du service du serveur de médiation est affiché sous la forme d’une coche verte. Si un X rouge apparaît à la place, sélectionnez le serveur de médiation. Dans le menu **action** , cliquez sur **Démarrer tous les services**.

Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, effectuez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveurs de médiation. Si vous n’avez pas besoin d’installer des fichiers pour le serveur de médiation pour d’autres ordinateurs, suivez les procédures décrites dans [Configuring Trunks in Lync server 2013](lync-server-2013-configuring-trunks.md) pour configurer les paramètres de la connexion de jonction entre ce pool de serveurs de médiation (ou tous les serveurs de médiation d’un site) et son homologue.

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

