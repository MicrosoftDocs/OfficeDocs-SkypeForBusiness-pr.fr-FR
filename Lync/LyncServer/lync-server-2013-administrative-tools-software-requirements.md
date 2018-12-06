---
title: "Lync Server 2013 : Conf. logicielle requise pour les outils d’administration"
TOCTitle: Configuration logicielle requise pour les outils d’administration
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg195653(v=OCS.15)
ms:contentKeyID: 49296759
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration logicielle requise pour les outils d’administration dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique présente les logiciels requis pour installer et utiliser les outils d’administration Lync Server 2013 ainsi que la configuration requise du système d’exploitation.

## Microsoft .NET Framework 4.5

L’édition 64 bits de Microsoft .NET Framework 4.5 est requise pour Lync Server 2013.

## Windows PowerShell 3.0

Windows PowerShell 3.0 est requis pour exécuter les composants de Microsoft Lync Server 2013. Pour plus d’informations, reportez-vous à [Installation de Windows PowerShell 3.0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Windows Installer version 4.5

Lync Server 2013 utilise la technologie Windows Installer pour installer, désinstaller et gérer différents rôles serveur. Windows Installer version 4.5 est disponible sous forme de composant redistribuable pour le système d’exploitation Windows Server. Windows Installer 4.5 est fourni avec Windows Server 2012 R2, Windows Server 2012 et Windows Server 2008 R2, ce qui signifie que vous n’avez pas à télécharger l’utilitaire pour les ordinateurs exécutant Lync Server 2013. ( Lync Server 2013 peut uniquement être installé sur les ordinateurs exécutant Windows Server 2012 R2, Windows Server 2012 ou Windows Server 2008 R2.)

Cependant, si vous souhaitez installer le générateur de topologie Lync Server Management Shell ou Lync Server sur un poste de travail d’administrateur, il se peut que vous deviez télécharger Windows Installer 4.5. Cet utilisateur est fourni avec Windows 7 et Windows 2008 R2 mais pas avec les versions précédentes du système d’exploitation Windows. Vous pouvez télécharger Windows Installer 4.5 depuis le Centre de téléchargement Microsoft à l’adresse <http://go.microsoft.com/fwlink/p/?linkid=197395>.

## Plug-in de navigateur Microsoft Silverlight 5

Le Panneau de configuration Lync Server 2013 est un outil web qui nécessite l’installation de la dernière version du plug-in du navigateur Microsoft Silverlight 5. Lorsque vous démarrez le Panneau de configuration Lync Server 2013, si ce logiciel n’est pas installé ou si une version antérieure est installée, le Panneau de configuration Lync Server 2013 vous invite à installer la version requise.

## Voir aussi

#### Concepts

[Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Autres ressources

[Configuration requise de l’infrastructure pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

