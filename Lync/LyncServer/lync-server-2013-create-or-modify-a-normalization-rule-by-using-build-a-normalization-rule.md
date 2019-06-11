---
title: Création ou modification d’une règle de normalisation à l’aide de l’onglet créer une règle de normalisation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 527510ac9b683df191414f5dffe456353d9cf277
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Créer ou modifier une règle de normalisation à l’aide de l’application créer une règle de normalisation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Pour créer ou modifier une règle de normalisation dans le panneau de configuration de Lync Server, procédez comme suit. Par ailleurs, si vous voulez créer ou modifier une règle de normalisation manuellement, voir [créer ou modifier une règle de normalisation manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>Pour définir une règle à l’aide de la création d’une règle de normalisation

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Facultatif Suivez les étapes de la rubrique [créer un plan de numérotation dans Lync server 2013 à l'](lync-server-2013-create-a-dial-plan.md) étape 11 ou [modifiez un plan de numérotation dans Lync Server 2013 à l'](lync-server-2013-modify-a-dial-plan.md) étape 10.

4.  Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **5DigitExtension**).

5.  (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).

6.  Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :
    
      - **Premiers chiffres**   (facultatifs) Spécifiez les premiers chiffres des numéros numérotés que vous voulez associer au modèle. Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.
    
      - **Longueur**   spécifiez le nombre de chiffres dans le modèle correspondant, puis indiquez si vous souhaitez que le modèle corresponde exactement à cette longueur, qu’il corresponde à des numéros qui utilisent au moins cette longueur ou qu’il corresponde à des numéros numérotés de n’importe quelle longueur.
    
      - **Chiffres à supprimer**   (facultatif) Spécifiez le nombre de chiffres de départ à supprimer des numéros numérotés que vous voulez associer au modèle.
    
      - **Chiffres à ajouter**   (facultatif) Spécifiez les chiffres à ajouter aux numéros numérotés à utiliser pour le modèle.
    
    Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**. Par exemple, si vous laissez vide le champ **Chiffres de début**, tapez **7** dans le champ **Longueur** et sélectionnez **Exactement**, puis spécifiez **0** dans le champ **Chiffres à supprimer**, l’expression régulière obtenue dans **Modèle à suivre** est :
    
    **^ (\\d{7}) $**

7.  Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :
    
      - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est **^ (\\j{7}) $** , **$1** dans la règle de traduction représente les numéros numérotés à 7 chiffres.
    
      - (Facultatif) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro converti (par exemple, **+1425**).
    
    Par exemple, si le modèle **à faire correspondre** contient **\\^{7}(d) $** en tant que modèle pour les numéros numérotés et la **règle de traduction** contenant **+ 1425 $1** comme modèle pour les numéros de téléphone E. 164, la règle normalise 5550100 à + 14255550100.

8.  (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

9.  (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    
    <div>
    

    > [!NOTE]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.

    
    </div>

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.

11. Cliquez sur **OK** pour enregistrer le plan de numérotation.

12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

