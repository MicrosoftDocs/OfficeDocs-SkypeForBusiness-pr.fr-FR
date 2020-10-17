---
title: Création ou modification d’une règle de normalisation à l’aide de la création d’une règle de normalisation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d4c6d5b8a8cd53cee9fdae0a38769a535b118
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508841"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Création ou modification d’une règle de normalisation à l’aide de la création d’une règle de normalisation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour créer ou modifier une règle de normalisation dans le panneau de configuration Lync Server, procédez comme suit. Par ailleurs, si vous souhaitez créer ou modifier une règle de normalisation manuellement, voir [créer ou modifier une règle de normalisation manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>Pour définir une règle à l’aide de la section Créer une règle de normalisation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Module Suivez les étapes de la procédure [créer un plan de numérotation dans Lync server 2013 à l'](lync-server-2013-create-a-dial-plan.md) étape 11 ou [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) à l’étape 10.

4.  Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **Postes5chiffres**).

5.  (Optionnel) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).

6.  Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :
    
      - **Chiffres**     de début Module Spécifiez les chiffres de début des numéros composés que le modèle doit respecter. Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.
    
      - **Longueur**     Spécifiez le nombre de chiffres dans le modèle de correspondance et indiquez si vous souhaitez que le modèle corresponde exactement à cette longueur, mettez en correspondance les numéros composés qui ont au moins cette longueur ou qui correspondent à des numéros de n’importe quelle longueur.
    
      - **Chiffres à supprimer**     Module Spécifiez le nombre de chiffres de début à supprimer des numéros composés que le modèle doit respecter.
    
      - **Chiffres à ajouter**     Module Spécifiez les chiffres à ajouter aux numéros composés que le modèle doit respecter.
    
    Les valeurs que vous entrez dans ces champs apparaissent dans **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous laissez vide le champ **Chiffres de début**, tapez **7** dans le champ **Longueur** et sélectionnez **Exactement**, puis spécifiez **0** dans le champ **Chiffres à supprimer**, l’expression régulière obtenue dans **Modèle à suivre** est :
    
    **^ ( \\ d {7} ) $**

7.  Dans **Règle de traduction**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 traduits :
    
      - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle de correspondance est **^ ( \\ d {7} ) $** Then **$1** dans la règle de conversion, représente les numéros composés à 7 chiffres.
    
      - (Optionnel) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro traduit (par exemple **+1425**).
    
    Par exemple, si le modèle **à faire correspondre** contient **^ ( \\ d {7} ) $** comme modèle pour les numéros composés et que la **règle de traduction** contient **+ 1425 $1** comme modèle pour les numéros de téléphone E. 164, la règle normalise 5550100 à + 14255550100.

8.  (Optionnel) Si la règle de normalisation se traduit par un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

9.  (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.
    
    <div>
    

    > [!NOTE]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.

    
    </div>

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.

11. Cliquez sur **OK** pour enregistrer le plan de numérotation.

12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

