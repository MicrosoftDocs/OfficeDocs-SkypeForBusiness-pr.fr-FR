---
title: 'Lync Server 2013: création ou modification d’une règle de stratégie de version de client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Créer ou modifier une règle de stratégie de nouvelle version du client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-21_

Les règles de stratégie de version du client définissent les actions qui doivent être effectuées lorsque les utilisateurs essaient de se connecter à l’aide de clients et de versions client spécifiques. Vous pouvez créer ou modifier des règles individuelles pour une stratégie de version de client à partir du panneau de configuration de Lync Server 2013.

<div>


> [!IMPORTANT]  
> Les règles sont classées par ordre de priorité. Par exemple, si vous avez une règle qui permet aux clients exécutant la version 1,5 de se connecter, suivi par une règle qui empêche les clients exécutant une version antérieure à 2,0, la première règle est prioritaire et les clients exécutant la version 1,5 sont autorisés à se connecter.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Pour créer ou modifier des règles de stratégie de version de client avec le panneau de configuration de Lync Server

1.  [Créez ou modifiez une nouvelle stratégie de version de client dans Lync server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) avec le panneau de configuration de Lync Server.

2.  Dans la page **modifier la stratégie de version du client** , effectuez l’une des opérations suivantes:
    
      - Cliquez sur **nouveau** pour créer une règle de version de client.
    
      - Cliquez sur l’un des types de clients définis dans la liste, puis sur **afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour indiquer le type de client.

    
    </div>

3.  Dans **agent utilisateur**, sélectionnez un type de client.

4.  Sous **numéro de version**, procédez comme suit:
    
      - Dans **version principale**, tapez le numéro qui correspond à la version majeure du client.
    
      - Dans **version mineure**, tapez le numéro qui correspond à la version mineure du client.
    
      - Dans **générer**, tapez le numéro qui correspond à la version majeure et mineure du client.
    
      - Dans **mise à jour**, tapez le numéro qui correspond à la version mise à jour du client.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour indiquer le numéro de version du client.

    
    </div>

5.  Pour spécifier l’opération correspondante pour la version du client spécifiée dans les étapes précédentes, dans **opération de comparaison**, cliquez sur l’une des options suivantes:
    
      - **Identique à**
    
      - **Différent de**
    
      - **Antérieur à**
    
      - **Antérieur ou simultané**
    
      - **Postérieur à**
    
      - **Postérieur ou simultané**

6.  Pour spécifier l’action à exécuter lorsque les critères spécifiés dans les étapes précédentes sont remplis, cliquez sur l’une **** des options suivantes:
    
      - Pour permettre au client de se connecter, cliquez sur **autoriser**.
    
      - Pour permettre au client de se connecter et de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update, cliquez sur **autoriser et mettre à niveau**. Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .
        
        <div>
        

        > [!NOTE]  
        > La sélection de cette action entraîne l’affichage d’une notification lors de la prochaine connexion de l’utilisateur à Lync 2013. La notification indique qu’une mise à jour est disponible, même si des mises à jour n’ont pas encore été publiées dans Windows Server Update service ou Microsoft Update. Pour éviter toute confusion, ne sélectionnez cette action qu’après que les mises à jour sont disponibles.

        
        </div>
    
      - Pour permettre au client de se connecter et d’afficher un message concernant l’emplacement de téléchargement d’une autre version du client, cliquez sur **autoriser avec une URL**. Vous spécifiez l’URL plus loin dans cette procédure.
    
      - Pour empêcher le client de se connecter, cliquez sur **bloquer**.
    
      - Pour empêcher le client de se connecter et de permettre au client de recevoir des mises à jour de Windows Server Update service ou Microsoft Update, cliquez sur **bloquer et mettre à niveau**. Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .
    
      - Pour empêcher le client de se connecter et d’afficher un message concernant l’emplacement de téléchargement d’une autre version du client, cliquez sur **bloquer avec l’URL**. Vous spécifiez l’URL plus loin dans cette procédure.

7.  Facultatif Si vous avez cliqué sur **autoriser avec** l’URL ou **bloquer avec l’URL** lors de l’étape précédente, tapez l’URL de téléchargement du client à inclure dans le message dans l' **URL**.

8.  Cliquez sur **OK**, puis sur **valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

