---
title: 'Lync Server 2013 : déploiement de clients Lync'
description: 'Lync Server 2013 : déploiement de clients Lync.'
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
ms.openlocfilehash: 09b501fc721ac880c5cf7da0293e3aa9c6443722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573430"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a>Déploiement de clients Lync dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lync 2013 présente une approche différente pour le déploiement de clients. Dans les versions antérieures, Lync 2013 ne dispose plus de son propre programme d’installation. Au lieu de cela, Lync est inclus dans le programme d’installation d’Office 2013. Pour déployer Lync 2013 auprès de vos utilisateurs, vous pouvez utiliser les méthodes d’installation et les outils de personnalisation d’Office 2013.

  - **Office 2013 Windows Installer** est un package d’installation basé sur Windows Installer qui se compose de plusieurs fichiers msi. Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet. Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Les rubriques de cette section décrivent comment utiliser et personnaliser Office 2013 Windows Installer pour déployer Lync 2013.

  - **Office 2013 « démarrer en un clic »** est un programme d’installation qui diffuse les fichiers d’installation d’Office à l’utilisateur à partir du centre d’administration Microsoft 365. Les administrateurs peuvent personnaliser l’installation à l’aide de l’outil Déploiement d’Office pour Office « Démarrer en un clic ». Étant donné que Office 2013 « démarrer en un clic » est principalement utilisé dans l’environnement Microsoft 365, cette méthode d’installation n’est pas décrite en détail dans cette section. Vous trouverez des informations détaillées sur l’utilisation et la personnalisation de l’installation d’Office « démarrer en un clic » dans la documentation du kit de ressources Office 2013. Les administrateurs peuvent également télécharger les fichiers de programme et de langue Office 2013 « démarrer en un clic » sur un emplacement local, ce qui est utile lorsque vous souhaitez réduire la demande sur le réseau ou empêcher les utilisateurs d’installer des logiciels à partir d’Internet en raison des exigences de sécurité de l’entreprise.

Les rubriques de cette section traitent de la façon de déployer des clients à l’aide du programme d’installation basé sur MSI Office 2013. Votre référence principale doit être la documentation du kit de ressources Office 2013, qui décrit en détail comment préparer votre infrastructure, personnaliser le programme d’installation et déployer Office 2013. Toutefois, vous devez utiliser la documentation Office conjointement avec les rubriques de cette section, qui indiquent les considérations de déploiement spécifiques à Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Le complément de réunion en ligne pour Lync 2013, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Lync 2013.</P>
> <LI>
> <P>Le programme d’installation d’Office 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator. Le client Lync 2013 installe côte à côte avec d’autres clients Lync ou Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Personnalisation de l’installation du client dans Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personnalisation du comportement de Lync et de l’interface utilisateur dans Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personnalisation du complément de réunion en ligne dans Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configuration de la page de participation aux réunions dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configuration des versions de client prises en charge dans Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configuration du mode de confidentialité améliorée de la présence dans Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

