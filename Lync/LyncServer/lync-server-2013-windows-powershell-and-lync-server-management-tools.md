---
title: 'Lync Server 2013 : Outils de gestion de Windows PowerShell et Lync Server 2013'
TOCTitle: Outils de gestion de Windows PowerShell et Lync Server 2013
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59679140
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Outils de gestion de Windows PowerShell et Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans Microsoft Lync Server 2013, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Les outils Lync Server 2013 qui sont implémentés à l’aide de Windows PowerShell incluent les éléments suivants :

  - **Générateur de topologie**. Vous utilisez le Générateur de topologie pour créer, ajuster et publier votre topologie planifiée. Il valide également votre topologie avant que vous ne commenciez à installer les serveurs. Lorsque vous installez Lync Server 2013 sur des serveurs individuels, les serveurs lisent la topologie déployée dans le cadre de leur processus d’installation, et le programme d’installation déploie le serveur comme décrit dans la topologie. Une fois l’installation effectuée, les informations de configuration sont répliquées automatiquement sur tous les serveurs. Les composants peuvent uniquement être ajoutés à votre déploiement en utilisant le Générateur de topologie.

  - **Lync Server Management Shell**. Vous pouvez utiliser Lync Server Management Shell pour une gestion complète de la ligne de commande de votre déploiement.

  - **Panneau de configuration Lync Server**. Vous pouvez utiliser l’interface utilisateur Panneau de configuration Microsoft Lync Server 2013 pour gérer les tâches les plus courantes de votre déploiement.

Ces outils utilisent les applets de commande Windows PowerShell pour la gestion de votre déploiement, à savoir près de 550 applets de commande spécifiques aux produits. Les applets de commande de sécurité incluses dans Lync Server 2013 sont principalement utilisées pour gérer l’authentification, ainsi que les droits et autorisations de l’utilisateur. Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN). En outre, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès basé sur un rôle (RBAC) pour déléguer le contrôle administratif de Lync Server 2013. Pour plus d’informations sur les applets de commande de Lync Server, voir [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation des opérations. Pour plus d’informations sur l’utilisation de Générateur de topologie et de Panneau de configuration Lync Server 2013 pour gérer votre déploiement, voir [Panneau de configuration Lync Server 2013](https://technet.microsoft.com/fr-fr/library/gg133224\(v=ocs.15\)) dans la documentation des opérations.

Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains problèmes de sécurité liés au script des technologies plus anciennes, y compris Microsoft Visual Basic Scripting Edition (VBScript). Les fonctionnalités de sécurité de Windows PowerShell sont conçues pour créer un environnement dans lequel les utilisateurs ne peuvent pas exécuter des scripts facilement ou inconsciemment. Par défaut, les fonctionnalités de sécurité de Windows PowerShell sont activées. Vous pouvez modifier l’état de ces fonctionnalités pour les adapter à vos besoins de script et à divers objectifs de sécurité. Cela ne veut pas dire que le shell empêche les utilisateurs d’exécuter des scripts. Mais plutôt, il est plus difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans en avoir conscience. Pour plus d’informations, voir Sécurité des scripts Windows PowerShell à l’adresse suivante : [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).

