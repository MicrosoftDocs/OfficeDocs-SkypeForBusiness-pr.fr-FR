---
title: Utilisation de Best Practices Analyzer pour analyser les problèmes éventuels dans votre déploiement
description: Utilisation de Best Practices Analyzer pour analyser les problèmes éventuels dans votre déploiement.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 032f5b46d8d5a28894e5f746e0cbc2aff6c5eaa2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567200"
---
# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Utilisation de Best Practices Analyzer pour analyser le déploiement de Lync Server 2013 à la recherche de problèmes éventuels

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Pour lancer une analyse Best Practices Analyzer, vous devez spécifier ce qui suit :

  - **Informations d’identification**     Pour exécuter une analyse, vous devez vous connecter à un ordinateur sur lequel Best Practices Analyzer est installé à l’aide d’un compte membre du groupe Administrateurs local. En outre, ce compte doit disposer des droits et autorisations requis pour lancer les analyses appropriées ou vous devez spécifier des informations d’identification disposant des droits et autorisations appropriés pour exécuter Best Practices Analyzer. Pour plus d’informations, reportez-vous aux [appartenances aux groupes et aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Étendue de l’analyse**     Pour spécifier l’étendue de l’analyse, sélectionnez les catégories et les serveurs que vous souhaitez analyser. Vous pouvez sélectionner toutes les catégories, une ou plusieurs catégories ou un ou plusieurs serveurs d’une catégorie spécifique dans votre environnement Lync Server.

  - **Type d’analyse**     Actuellement, l’analyse du contrôle d’intégrité est le seul type d’analyse disponible (sélectionné par défaut). L’analyse de vérification de l’intégrité génère un rapport qui comprend les erreurs, les avertissements et d’autres informations pour tous les serveurs spécifiés dans l’étendue de l’analyse.

  - **Vitesse**     du réseau Les options de vitesse du réseau sont les suivants : Fast LAN (100 Mbits/s ou plus), LAN (10 Mbits/s), Fast WAN (1,5 Mbits/s) ou WAN (64 Kbits/s). Le temps estimé pour réaliser l’analyse dépend de ce paramètre. Ce paramètre est également utilisé pour définir le délai d’expiration. Au cours de l’analyse, Best Practices Analyzer attend une réponse d’un serveur dans un délai spécifié. S’il ne reçoit aucune réponse dans ce délai, il passe au serveur suivant dans l’analyse. Sur les réseaux plus lents, ce délai est plus long pour prendre en compte les latences réseau plus longues. Nous vous recommandons de sélectionner la liaison la plus lente dans votre topologie pour ce paramètre afin que l’exécution de l’outil n’expire pas non plus.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Pour analyser votre déploiement Lync Server 2013

1.  Ouvrez une session sur un ordinateur, sur lequel Best Practices Analyzer est installé, avec un compte membre du groupe Administrateurs local et qui dispose d’autres droits et autorisations requis.

2.  Cliquez sur **Démarrer**, pointez sur **tous les programmes**, cliquez sur **Microsoft Lync Server 2013**, puis sur **Best Practices Analyzer**.

3.  Dans l’écran d’**accueil**, cliquez sur **Sélectionner des options pour une nouvelle analyse**.

4.  Dans la page **Connexion à Active Directory**, vérifiez le nom spécifié dans **Serveur Active Directory**, puis effectuez l’une des opérations suivantes :
    
      - Pour lancer une analyse avec les informations d’identification que vous avez utilisées pour ouvrir une session sur l’ordinateur, cliquez sur **Connexion au serveur Active Directory**.
    
      - Pour spécifier d’autres informations d’identification que celles que vous souhaitez utiliser pour les services de domaine Active Directory, les serveurs Edge ou les serveurs Exchange, cliquez sur **Afficher les options d’ouverture de session avancées**, activez les cases à cocher pour lesquelles des informations d’identification distinctes sont requises, spécifiez les informations d’identification pour chacune des cases à cocher activées, puis cliquez sur **Connexion au serveur Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Avant de commencer l’analyse, Best Practices Analyzer effectue une vérification du réseau et des autorisations pour s’assurer que les informations d’identification spécifiées sont valides et qu’il peut se connecter aux services de domaine Active Directory. Si l’outil est exécuté sur un serveur de groupe de travail, il vérifie également qu’il peut se connecter aux serveurs Edge dans le réseau de périmètre (s’ils sont inclus dans l’analyse).

    
    </div>

5.  Dans la page **Démarrer une nouvelle analyse Best Practices**, sélectionnez les options que vous souhaitez inclure dans l’analyse, spécifiez la vitesse du réseau, puis cliquez sur **Démarrer l’analyse**.

6.  Dans la page **Analyse terminée**, cliquez sur **Afficher un rapport de cette analyse**.

7.  Dans la page **Afficher le rapport Best Practices**, effectuez l’une des opérations suivantes :
    
      - Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **Rapports de liste**, puis cliquez sur l’onglet **Tous les problèmes** ou sur l’onglet **Éléments d’information**.
    
      - Pour afficher les rapports sous forme de liste hiérarchique organisée par type de résultat, cliquez sur **Rapports d’arborescence**, puis cliquez sur l’onglet **Affichage détaillé** ou sur l’onglet **Affichage de synthèse**.
    
      - Pour afficher d’autres rapports, cliquez sur **Autres rapports**.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations sur les rapports de Best Practices Analyzer et les problèmes qu’ils identifient, voir <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">affichage et utilisation des rapports créés par Best Practices Analyzer dans Lync server 2013</A> et <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analyse et résolution des problèmes identifiés par Best Practices Analyzer dans Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

