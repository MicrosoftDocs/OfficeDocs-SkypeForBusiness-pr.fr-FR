---
title: 'Lync Server 2013 : renforcement et protection des serveurs et des applications'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Renforcement et protection des serveurs et des applications pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-12-05_

Vous devez renforcer et protéger votre système d’exploitation et vos applications conformément aux meilleures pratiques pour ce composant spécifique. Cette section explique comment renforcer les serveurs d’applications et utiliser une stratégie de groupe pour implémenter les verrouillages de sécurité.

<div>


> [!NOTE]  
> Vous pouvez également renforcer et protéger les bases de données utilisées pour le déploiement de Microsoft Lync Server 2013. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hardening-and-protecting-databases.md">la rubrique renforcement et protection des bases de données de Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Sécurisation des serveurs d’applications

Pour les serveurs d’applications, le système d’exploitation et l’application doivent être renforcés. Par exemple, un ordinateur Windows Server 2008 destiné à exécuter Microsoft Internet Security and Acceleration (ISA) Server 2006 doit être renforcé à partir du système d’exploitation et du point de vue de l’application. Il est préférable de réduire le nombre de services en cours d’exécution et fournis par le serveur.

</div>

<div>

## <a name="securing-virtual-servers"></a>Sécurisation des serveurs virtuels

Les instantanés du serveur virtuel contiennent des copies des disques de données du serveur et contiennent également des vidages de données en mémoire, qui peuvent contenir des données de chiffrement sensibles susceptibles de provoquer des attaques. Pour les serveurs de production implémentés à l’aide de la virtualisation, il est recommandé de désactiver toutes les captures d’instantanés serveur ou de les gérer de manière très contrôlée. Pour plus d’informations sur la sécurisation des serveurs virtuels Hyper-V, voir le guide sur [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)la sécurité Hyper-v sur le:.

</div>

<div>

## <a name="group-policy"></a>Stratégie de groupe

Dans Windows Server 2008 et Windows Server 2008 R2, la stratégie de groupe fournit la gestion de la configuration de bureau basée sur un annuaire. Vous pouvez utiliser une stratégie de groupe pour implémenter les verrouillages de sécurité en définissant des paramètres d’ordinateur et d’utilisateur au sein d’un objet de stratégie de groupe pour les éléments suivants:

  - Stratégies basées sur le registre

  - Sécurité

  - Installation de logiciels

  - Scripts

  - Redirection de dossiers

  - Services d’installation à distance

Pour fournir une interface utilisateur permettant à l’administrateur de configurer ces paramètres, les modèles d’administration sont livrés avec les versions de système d’exploitation, les versions de Service Pack et certaines applications, y compris Lync Server 2013.

Le fichier Communicator. adm est un modèle d’administration fourni avec Lync Server 2013, qui est installé sur le répertoire% windir\\%\\ INF et fournit une interface aux paramètres de stratégie de groupe. Chaque paramètre dans Communicator. adm correspond à un paramètre du Registre affectant le comportement de l’application.

Il est possible d’accéder aux paramètres à partir de GPedit. dll, qui est disponible dans la console utilisateurs et ordinateurs Active Directory et la console de gestion des stratégies de groupe (GPMC).

</div>

<div>

## <a name="group-policy-security-settings"></a>Paramètres de sécurité de stratégie de groupe

La stratégie de groupe contient les paramètres de sécurité d’un objet de stratégie de groupe sous Configuration ordinateur/Paramètres Windows/paramètres de sécurité lorsqu’il est consulté à partir de GPedit. dll. Vous pouvez importer des modèles de sécurité pour configurer les paramètres de sécurité de l’objet de stratégie de groupe. Le guide sur la sécurité de Windows [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) Server 2008 de et le kit de gestion de la sécurité [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) Windows Server 2008 R2 Security Compliance pour contiennent un certain nombre d’exemples de modèles que vous pouvez modifier en fonction de vos besoins.

</div>

<div>

## <a name="best-practices"></a>Meilleures pratiques

  - Renforcez tous les systèmes d’exploitation et applications du serveur.

  - Protéger les clichés du serveur et renforcer la sécurité de tous les serveurs virtuels.

  - Utiliser une stratégie de groupe pour implémenter les verrouillages de sécurité.

</div>

</div>

<span> </span>

</div>

</div>

</div>

