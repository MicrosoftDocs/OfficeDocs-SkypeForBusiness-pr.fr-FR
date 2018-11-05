---
title: 'Lync Server 2013 : Installation des outils d’administration Lync Server'
TOCTitle: Installation des outils d’administration Lync Server
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398665(v=OCS.15)
ms:contentKeyID: 49297927
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des outils d’administration Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Cette rubrique explique comment installer les outils d’administration nécessaires pour déployer et gérer Lync Server 2013. Ils sont installés par défaut sur chaque serveur exécutant Lync Server 2013. Par ailleurs, vous pouvez installer ces outils sur d’autres ordinateurs, notamment sur des consoles d’administration dédiées. Il est vivement recommandé de les installer sur un ordinateur faisant partie du même domaine ou forêt que le déploiement Lync Server 2013 que vous créez, car cette méthode garantit que la procédure de préparation de services de domaine Active Directory est déjà terminée. Vous pouvez ainsi utiliser ultérieurement les outils d’administration sur cet ordinateur pour publier votre topologie.

Veillez à prendre connaissance des spécifications concernant l’infrastructure, le système d’exploitation, les logiciels et les droits d’administrateur avant d’installer ou d’utiliser les outils d’administration Lync Server 2013 . Pour plus d’informations sur les spécifications de l’infrastructure, reportez-vous à [Configuration requise de l’infrastructure pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Pour plus d’informations sur la configuration requise concernant le système d’exploitation et les logiciels pour installer les outils d’administration Lync Server 2013, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) et à [Autres prises en charge et configurations de serveur requises dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Pour plus d’informations sur les droits et les autorisations utilisateur requis pour installer et utiliser ces mêmes outils, reportez-vous à [Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

> [!IMPORTANT]  
> Si votre organisation exige que les services Internet (IIS) et l’ensemble des services web soient placés sur un lecteur autre que le lecteur système, vous pouvez modifier l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue Installation. Si vous installez les fichiers d’installation à cet emplacement, dont OCSCore.msi, les fichiers Lync Server 2013 restants seront également déployés sur ce lecteur.

## Pour installer les outils d’administration de Lync Server 2013

1.  Connectez-vous en tant qu’administrateur local (minimum requis) à l’ordinateur sur lequel vous souhaitez installer les outils d’administration. Si vous êtes connecté en tant qu’utilisateur standard sur les systèmes d’exploitation Windows Vista ou Windows 7 et que le contrôle de compte d’utilisateur (UAC) est activé, vous devez entrer votre nom d’utilisateur et votre mot de passe en qualité d’administrateur local ou ceux d’un domaine équivalent.

2.  Accédez au support d’installation sur votre ordinateur, puis double-cliquez sur \\Setup\\amd64\\Setup.exe.

3.  Si le système vous invite à installer le package distribuable Microsoft Visual C++ 2008, cliquez sur **Oui**.

4.  Dans la page **Emplacement d’installation de Microsoft Lync Server 2013**, cliquez sur **OK**. Remplacez ce chemin par le chemin d’accès à un autre emplacement ou lecteur si vous souhaitez que les fichiers soient installés à un autre endroit.
    
    > [!IMPORTANT]  
    > Si votre organisation exige que les services Internet (IIS) et l’ensemble des services web soient placés sur un lecteur autre que le lecteur système, vous pouvez modifier l’emplacement d’installation des fichiers Lync Server 2013 dans la boîte de dialogue Installation. Si vous installez les fichiers d’installation à cet emplacement, dont OCSCore.msi, les fichiers Lync Server 2013 restants seront également déployés sur ce lecteur.

5.  Dans la page **Contrat de Licence Utilisateur Final**, vérifiez les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est obligatoire pour continuer.

6.  Dans la page **Microsoft Lync Server 2013 – Assistant Déploiement**, cliquez sur **Installer les outils d’administrateur**.

7.  Lorsque l’installation est terminée cliquez sur **Quitter**.

## Voir aussi

#### Tâches

[Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md)  

#### Concepts

[Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)

