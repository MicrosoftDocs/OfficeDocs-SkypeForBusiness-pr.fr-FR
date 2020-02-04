---
title: 'Lync Server 2013 : exécuter des tests de routage de voix informels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Exécuter des tests de routage de voix informels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

Vous pouvez utiliser la boîte de dialogue **créer des informations de cas de test de routage de voix** pour exécuter des tests informels avant de créer un cas de test réel. Lorsque vous êtes satisfait du résultat d’un test, vous pouvez l’enregistrer comme un cas de test formel.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>Pour exécuter un test de routage vocal informel

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales**, puis cliquez sur **tester le routage vocal**.

4.  Dans la page **test de routage vocal** , cliquez sur **créer des informations de cas de test de routage vocal**.

5.  Dans le champ **numéro composé** , entrez le numéro de téléphone que vous voulez utiliser pour ce test. Ce numéro sera normalisé et affiché dans le champ **nombre normalisé** du volet **résultats** .

6.  Dans la liste **plan de numérotation** , sélectionnez le plan de numérotation à utiliser pour tester le numéro numéroté. Par défaut est le plan de numérotation global.
    
    Lors de l’exécution du test, la première règle de normalisation de ce plan de numérotation qui correspond au numéro composé sera affichée dans le champ **règle de normalisation** du volet **résultats** .

7.  Dans la liste **politique vocale** , sélectionnez la stratégie vocale à utiliser pour tester le numéro numéroté. La valeur par défaut est la stratégie de voix globale.
    
    Lors de l’exécution du test, le premier enregistrement d’utilisation RTC correspondant à cette stratégie vocale est affiché dans le premier champ d' **utilisation RTC** du volet **résultats** . Par ailleurs, le premier itinéraire vocal correspondant associé à cet enregistrement d’utilisation RTC sera affiché dans le premier champ de **routage** .

8.  Facultatif Activez la case à cocher **remplir à partir de l’utilisateur** si vous souhaitez tester le numéro numéroté par rapport à la stratégie vocale attribuée à un utilisateur particulier.
    
    1.  Cliquez sur **Parcourir** pour afficher la boîte de dialogue **Sélectionner des utilisateurs voix entreprise** .
    
    2.  Cliquez sur **Rechercher** pour afficher la liste des utilisateurs activés pour voix entreprise.
    
    3.  Double-cliquez sur le nom d’utilisateur dont vous souhaitez utiliser la politique vocale affectée pour ce test. Le champ **politique** est désormais rempli par la stratégie vocale affectée à l’utilisateur sélectionné.
    
    Lors de l’exécution du test, le premier enregistrement d’utilisation RTC (réseau téléphonique commuté) correspondant à cette stratégie vocale sera affiché dans le **premier champ d’utilisation RTC** du volet **résultats** . Par ailleurs, le premier itinéraire vocal correspondant associé à cet enregistrement d’utilisation RTC sera affiché dans le premier champ de **routage** .

9.  Cliquez sur **exécuter** pour exécuter le cas de test. Les résultats sont affichés dans le volet droit de la boîte de dialogue.

10. Facultatif Cliquez sur **Enregistrer sous** si vous voulez enregistrer cette configuration de test en tant que cas de test formel.
    
    1.  Dans le champ **nom** de la boîte de dialogue **enregistrer les informations de cas de test de routage de voix** , tapez un nom unique pour le cas de test.
        
        Ce nom doit être unique parmi les cas de test de routage vocal dans votre déploiement voix entreprise. Il peut y avoir une longueur maximale de 32 caractères et contenir des caractères alphanumériques, en plus de la barre\\oblique inverse (), du point (.) ou\_du trait de soulignement ().
    
    2.  Notez que les champs restants de la boîte de dialogue Enregistrer les informations de cas de test de l' **itinéraire vocale** sont en lecture seule et sont préremplis par rapport à la configuration *et* aux résultats du test informel. Vérifiez qu’il s’agit de la configuration que vous voulez enregistrer pour le cas de test.
        
        <div>
        

        > [!NOTE]  
        > Les valeurs des résultats de test permettent de préremplir les champs de la boîte de dialogue Enregistrer les informations de cas de test de l' <STRONG>acheminement du message</STRONG> , comme suit : 
        > <UL>
        > <LI>
        > <P>La <STRONG>traduction attendue</STRONG> est préremplie avec la valeur du champ <STRONG>nombre normalisé</STRONG> .</P>
        > <LI>
        > <P>Le champ <STRONG>route attendu</STRONG> est pré-rempli avec la valeur du <STRONG>premier champ itinéraire</STRONG> .</P>
        > <LI>
        > <P>L' <STRONG>enregistrement d’utilisation RTC attendu</STRONG> est pré-rempli avec la valeur du premier champ d' <STRONG>utilisation PSTN</STRONG> .</P></LI></UL>Si les correspondances pour une de ces valeurs n’ont pas été trouvées lors de la série de tests, le champ correspondant est vide dans la boîte de dialogue Enregistrer les informations de cas de test de l' <STRONG>acheminement du message</STRONG> .

        
        </div>
    
    3.  Cliquez sur **OK** pour enregistrer le cas de test, ou cliquez sur **Annuler** pour revenir à la boîte de dialogue Afficher les informations de cas de **test de routage**

11. Cliquez sur **Valider**, puis sur **Tout valider**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez un cas de test de routage de voix, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier le cas de test. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’un cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Exécuter des cas de test de routage de voix dans Lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
[Exportation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

