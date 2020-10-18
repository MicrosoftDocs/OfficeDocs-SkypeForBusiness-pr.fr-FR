---
title: 'Lync Server 2013 : création ou modification d’une règle de stratégie de version du client'
description: 'Lync Server 2013 : création ou modification d’une règle de stratégie de version du client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574620"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Création ou modification d’une nouvelle règle de stratégie de version des clients dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-21_

Les règles de stratégie de version des clients définissent les actions à entreprendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques. Vous pouvez créer ou modifier des règles individuelles pour une stratégie de version de client à partir du panneau de configuration Lync Server 2013.

<div>


> [!IMPORTANT]  
> Les règles sont répertoriées par ordre de priorité. Par exemple, si vous avez une règle qui permet aux clients exécutant la version 1,5 de se connecter, suivi d’une règle qui bloque les clients exécutant une version antérieure à 2,0, la première règle prend la priorité et les clients exécutant la version 1,5 sont autorisés à se connecter.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Pour créer ou modifier des règles de stratégie de version des clients à l’aide du panneau de configuration Lync Server

1.  [Créez ou modifiez une nouvelle stratégie de version du client dans Lync server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) avec le panneau de configuration Lync Server.

2.  Sur la page **modifier la stratégie de version du client** , effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Nouveau** pour créer une règle de version du client.
    
      - Cliquez sur l’un des types de clients définis dans la liste, puis sur **Afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour spécifier le type du client.

    
    </div>

3.  Dans **Agent utilisateur**, sélectionnez un type de client.

4.  Sous **Numéro de version**, procédez comme suit :
    
      - Dans **Version principale**, tapez le numéro qui correspond à la version principale du client.
    
      - Dans **Version secondaire**, tapez le numéro qui correspond à la version secondaire du client.
    
      - Dans **Version**, tapez le numéro qui correspond aux versions principale et secondaire du client.
    
      - Dans **Mise à jour**, tapez le numéro qui correspond à la version mise à jour du client.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser des caractères génériques pour spécifier le numéro de version du client.

    
    </div>

5.  Pour sélectionner l’opération de comparaison à utiliser pour la version du client spécifiée ci-dessus, dans **Opération de comparaison**, cliquez sur l’une des options suivantes :
    
      - **Identique à**
    
      - **N’est pas**
    
      - **Plus récent que**
    
      - **Plus récent ou identique**
    
      - **Plus ancien que**
    
      - **Plus ancien ou identique**

6.  Pour spécifier l’action à exécuter lorsque les critères définis ci-dessus sont respectés, cliquez sur l’une des options suivantes dans **Action** :
    
      - Pour autoriser le client à se connecter, cliquez sur **Autoriser**.
    
      - Pour autoriser le client à se connecter et à recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Autoriser et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.
        
        <div>
        

        > [!NOTE]  
        > La sélection de cette action entraîne l’affichage d’une notification la prochaine fois que les utilisateurs se connectent à Lync 2013. La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées dans le service de mise à jour de Windows Server ou dans Microsoft Update. Pour éviter toute confusion, vous avez tout intérêt à choisir cette action après que des mises à jour ont été mises à disposition uniquement.

        
        </div>
    
      - Pour autoriser le client à se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Autoriser avec une URL**. Vous indiquerez l’URL ultérieurement.
    
      - Pour empêcher le client de se connecter, cliquez sur **Bloquer**.
    
      - Pour empêcher le client de se connecter et lui permettre de recevoir des mises à jour de Windows Server Update Service ou Microsoft Update, cliquez sur **Bloquer et mettre à niveau**. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.
    
      - Pour empêcher le client de se connecter et afficher un message sur l’emplacement de téléchargement d’une autre version du client, cliquez sur **Bloquer avec une URL**. Vous indiquerez l’URL ultérieurement.

7.  (Facultatif) Si vous avez cliqué sur **Autoriser avec une URL** ou **Bloquer avec une URL** à l’étape précédente, dans le champ **URL**, tapez l’URL de téléchargement du client que vous souhaitez inclure dans le message.

8.  Cliquez sur **OK**, puis sur **valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

