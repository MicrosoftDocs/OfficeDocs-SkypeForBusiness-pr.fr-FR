---
title: 'Lync Server 2013 : déploiement de clients Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Déploiement de clients Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lync 2013 introduit une approche différente pour le déploiement du client. À partir de versions précédentes, Lync 2013 ne dispose plus de son propre programme d’installation. À la place, Lync est inclus avec le programme d’installation d’Office 2013. Pour déployer Lync 2013 auprès des utilisateurs, vous pouvez utiliser les méthodes d’installation d’Office 2013 et les outils de personnalisation.

  - Le programme d’installation d' **Office 2013** est un package d’installation basé sur Windows Installer, composé de plusieurs fichiers msi. Un package MSI de base indépendant de la langue est associé à un ou plusieurs packages spécifiques à la langue pour créer un produit complet. La configuration assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Les rubriques de cette section expliquent comment utiliser et personnaliser le programme d’installation de Windows 2013 pour déployer Lync 2013.

  - **Office 2013 démarrer** en un clic est un programme d’installation qui diffuse les fichiers d’installation d’Office à l’utilisateur à partir du portail Microsoft Office 365. Les administrateurs peuvent personnaliser l’installation à l’aide de l’outil Déploiement d’Office pour « Démarrer en un clic ». Comme Office 2013 démarrer en un clic est essentiellement utilisé dans l’environnement Microsoft Office 365, cette méthode d’installation n’est pas décrite en détail dans cette section. Des informations détaillées sur l’utilisation et la personnalisation de l’installation « démarrer en un clic » sont disponibles dans la documentation du kit de ressources Office 2013. Les administrateurs peuvent également télécharger le programme Office 2013 « démarrer en un clic » et les fichiers source de langue vers un emplacement local, ce qui est utile lorsque vous souhaitez réduire la demande sur le réseau ou empêcher les utilisateurs d’installer un logiciel à partir d’Internet en raison de exigences en matière de sécurité d’entreprise.

Les rubriques de cette section portent sur le déploiement de clients à l’aide du programme d’installation MSI d’Office 2013. Il doit s’agir de la documentation du kit de ressources Office 2013, qui décrit en détail la préparation de votre infrastructure, la personnalisation de l’installation et le déploiement d’Office 2013. Néanmoins, vous devez utiliser la documentation Office conjointement avec les rubriques de cette section, qui pointent sur des considérations de déploiement spécifiques à Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Le complément réunion en ligne pour Lync 2013, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Lync 2013.</P>
> <LI>
> <P>Le programme d’installation d’Office 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator. Le client Lync 2013 s’installe côte à côte avec d’autres clients Lync ou Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Personnalisation de l’installation du client dans Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personnalisation du comportement de Lync et de l’interface utilisateur dans Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personnalisation du complément réunion en ligne dans Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configuration des versions clientes prises en charge dans Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configuration du mode de confidentialité Enhanced presence dans Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

