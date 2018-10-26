---
title: Déploiement des clients Lync dans Lync Server 2013
TOCTitle: Déploiement des clients Lync dans Lync Server 2013
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204827(v=OCS.15)
ms:contentKeyID: 49296958
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des clients Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-03_

Lync 2013 introduit une approche différente du déploiement de clients. Contrairement aux versions précédentes, Lync 2013 ne possède plus son propre programme d’installation. De fait, Lync est intégré au programme d’installation d’Office 2013. Pour déployer Lync 2013 pour vos utilisateurs, vous pouvez utiliser les méthodes d’installation et les outils de personnalisation d’Office 2013.

  - **Office 2013 Windows Installer** est un package d’installation basé sur Windows Installer qui est constitué de plusieurs fichiers MSI. Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet. Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs. Les rubriques de cette section expliquent comment utiliser et personnaliser Office 2013 Windows Installer pour déployer Lync 2013.

  - **Office 2013 « Démarrer en un clic »** est un programme d’installation qui transmet en continu les fichiers d’installation Office à l’utilisateur à partir du portail Microsoft Office 365. Les administrateurs peuvent personnaliser l’installation à l’aide de l’outil Déploiement d’Office pour Office « Démarrer en un clic ». Office 2013 « Démarrer en un clic » étant principalement utilisé dans l’environnement Microsoft Office 365, cette méthode d’installation n’est pas décrite en détail dans cette section. En revanche, vous trouverez des informations détaillées sur l’utilisation et la personnalisation de l’installation d’Office « Démarrer en un clic » dans la documentation Kit de ressources Office 2013. Les administrateurs peuvent aussi télécharger le programme et les fichiers sources de langue Office 2013 « Démarrer en un clic » à un emplacement local, ce qui s’avère utile pour limiter la demande sur le réseau ou empêcher les utilisateurs d’installer le logiciel à partir d’Internet, en vertu des règles de sécurité de l’entreprise.

Les rubriques de cette section s’intéressent essentiellement au déploiement des clients par le biais du programme d’installation MSI d’Office 2013. La source de référence à privilégier est la documentation Kit de ressources Office 2013, qui explique en détail comment préparer l’infrastructure, personnaliser l’installation et déployer Office 2013. Toutefois, il vous sera utile de consulter également les rubriques de cette section, qui mettent en avant des aspects du déploiement spécifiques à Lync 2013.

> [!NOTE]  
> <ul>
> <li><p>Le complément de réunion en ligne pour Lync 2013, qui permet de gérer les réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Lync 2013.</p></li>
> <li><p>Le programme d’installation Office 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator. Le client Lync 2013 s’installe côte à côte avec les autres clients Lync ou Office Communicator.</p></li></ul>


## Dans cette section

  - [Personnalisation de l’installation du client](lync-server-2013-customizing-client-installation.md)

  - [Personnalisation du comportement de Lync et de l’interface utilisateur](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personnalisation du complément de réunion en ligne dans Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configuration des versions du client prises en charge](lync-server-2013-configuring-supported-client-versions.md)

  - [Configuration du mode de confidentialité améliorée de la présence](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

