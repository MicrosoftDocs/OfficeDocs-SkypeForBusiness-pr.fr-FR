---
title: 'Lync Server 2013 : Installation de la base de données de serveur Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Installation de la base de données de serveur Standard Edition pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

La configuration d’un serveur Standard Edition Server en tant que serveur unique dans votre infrastructure qui est identique à celle d’autres installations de serveur dans le cadre de l' **Assistant Déploiement** est une sélection spécifique à la configuration du serveur initial.

<div>

## <a name="to-install-a-standard-edition-server"></a>Pour installer un serveur Standard Edition Server

1.  Ouvrez une session sur le serveur sur lequel vous allez installer Standard Edition Server en tant qu’administrateur local ou un domaine équivalent.

2.  Si vous n’avez pas encore préparé les services de domaine Active Directory, vous devez d’abord effectuer ces procédures. Pour plus d’informations, consultez [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **préparer le premier serveur Standard Edition**.

4.  Sur la page **préparer Single Standard Edition Server** , cliquez sur **suivant**.

5.  Sur la page **exécution des commandes** , SQL Server 2012 Express est installé en tant que magasin de gestion centrale. Des règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et du logiciel requis est terminée, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > L’installation initiale risque de prendre un certain temps sans qu’aucune mise à jour ne s’affiche à l’écran de synthèse de la sortie de commande. Le problème est dû à l’installation de SQL Server Express. Si vous avez besoin de surveiller l’installation de la base de données, utilisez le gestionnaire des tâches pour contrôler la configuration.

    
    </div>

6.  Dans la page Assistant Déploiement de Lync Server, cliquez sur **installer le générateur de topologie** si vous n’avez pas encore installé les outils d’administration. Pour en savoir plus, voir [installer les outils d’administration de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Vérifiez que la case à cocher «préparer Active Directory» et «préparer le premier serveur Standard Edition» et «installer le générateur de topologie» est activée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

