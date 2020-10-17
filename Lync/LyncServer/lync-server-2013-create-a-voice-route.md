---
title: 'Lync Server 2013 : création d’un itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e45404dcd280f4c4eb5337ba4e1a8c1337b409f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501791"
---
# <a name="create-a-voice-route-in-lync-server-2013"></a>Créer un itinéraire des communications vocales dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

La procédure suivante explique comment créer un nouvel itinéraire des communications vocales à l’aide du panneau de configuration Lync Server 2013. Pour modifier un itinéraire existant, reportez-vous à la rubrique [modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) pour la procédure.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Pour créer un itinéraire des communications vocales à l’aide du panneau de configuration Lync Server

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Cliquez sur **Itinéraire**.

5.  Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire de communications vocales**.

6.  Dans **nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.

7.  Module Dans **Description**, entrez des informations descriptives supplémentaires pour l’itinéraire des communications vocales.

8.  Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez soit utiliser l’outil **créer un modèle pour faire correspondre** pour générer une expression régulière, soit écrire l’expression régulière manuellement.
    
      - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
        
          - **Chiffres de départ pour les nombres que vous souhaitez autoriser :** Entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le +, le cas échéant). Par exemple, tapez **+ 425**, puis cliquez sur **Ajouter**. Répétez cette opération pour chaque valeur de préfixe que vous souhaitez inclure dans l’itinéraire.
        
          - **Exceptions :** Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants que vous ne voulez *pas* que cet itinéraire s’intègre. Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez une valeur de **+ 425237** dans le champ **exceptions** , puis cliquez sur **OK**.
    
      - Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis saisissez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET Framework regular expressions » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

9.  Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **Autre ID de l’appelant** qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.

10. Pour associer une ou plusieurs jonctions à l’itinéraire des communications vocales, cliquez sur **Ajouter** , puis sélectionnez une jonction dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Si votre déploiement inclut des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils seront également disponibles dans la liste.

    
    </div>

11. Pour associer une ou plusieurs utilisations RTC (réseau téléphonique commuté) à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation RTC qui ont été définis pour votre déploiement voix entreprise.
    
    <div>
    

    > [!NOTE]  
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, reportez-vous à la rubrique <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage Records in Lync Server 2013</A>.<BR>Pour créer ou modifier des enregistrements d’utilisation RTC, reportez-vous à <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</A>.

    
    </div>

12. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!NOTE]  
    > Contrairement à une stratégie de voix, dans laquelle l’ordre dans lequel sont répertoriés les enregistrements d’utilisation RTC est important, l’ordre dans lequel les enregistrements d’utilisation RTC sont répertoriés dans l’itinéraire des communications vocales n’est pas significatif. Toutefois, nous vous recommandons d’organiser la liste par fréquence d’utilisation. Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server parcourt la liste du haut vers le bas.)

    
    </div>

13. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer un itinéraire de communications vocales qui ne réussit pas encore le test, puis le reconfigurer par la suite. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.

    
    </div>

14. Cliquez sur **OK** pour enregistrer l’itinéraire de communications vocales.

<div>


> [!IMPORTANT]  
> Chaque fois que vous créez un itinéraire des communications vocales, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">la rubrique publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Afficher les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

