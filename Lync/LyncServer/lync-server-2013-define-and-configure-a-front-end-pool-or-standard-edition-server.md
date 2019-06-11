---
title: Définition et configuration d’un pool frontal ou d’un serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-08_

Cette procédure ne nécessite pas d’appartenance à un administrateur local ou à un groupe de domaines privilégiés. Vous devez vous connecter à un ordinateur en tant qu’utilisateur standard.

Si vous déployez un serveur d’entreprise, un nombre minimum de serveurs frontaux dans un pool doit être en cours d’exécution. Le tableau suivant récapitule ces exigences.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs frontaux de la liste</th>
<th>Nombre de serveurs devant être exécutés pour que le pool soit opérationnel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Pour Lync Server 2013, chaque fois que vous ajoutez ou supprimez un serveur frontal de la liste, vous devez redémarrer les services. La suppression et l’ajout de serveurs doivent être effectuées en tant qu’opérations séparées. Par exemple, si vous envisagez d’ajouter deux serveurs frontaux et de supprimer deux serveurs frontaux, procédez comme suit: 
> <OL>
> <LI>
> <P>Supprimez les deux serveurs frontaux.</P>
> <LI>
> <P>Publiez et réactivez la topologie.</P>
> <LI>
> <P>Redémarrer les services</P>
> <LI>
> <P>Ajoutez les deux serveurs front-end.</P>
> <LI>
> <P>Publiez et réactivez la topologie.</P>
> <LI>
> <P>Redémarrez les services.</P></LI></OL>



</div>

Après avoir défini votre topologie, utilisez la procédure suivante pour définir un pool frontal pour votre site. Pour plus d’informations sur la définition de la topologie, voir [définir et configurer une topologie dans le générateur de topologies pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Pour définir un pool frontal

1.  Dans l’Assistant définir un nouveau pool frontal, dans la page **définir le nouveau pool frontal** , cliquez sur **suivant**.

2.  Dans la page **définir le nom de domaine complet du pool frontal** , entrez un nom de domaine complet (FQDN) pour le pool que vous **** êtes en train de créer, puis cliquez sur **suivant**.

3.  Dans la page **définir les ordinateurs de ce pool** , entrez un nom de domaine complet pour le premier serveur frontal de la liste, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les ordinateurs que vous voulez ajouter à la liste, puis cliquez sur **suivant**.

4.  Dans la page **Sélectionner des fonctionnalités** , activez les cases à cocher des fonctionnalités que vous voulez inclure dans ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher **conférences** pour autoriser la messagerie instantanée à plusieurs éléments, mais pas la sélection des conférences rendez **-vous (RTC)**, **voix entreprise**ou ** **Cases à cocher contrôle d’admission des appels, car elles représentent les fonctionnalités de conférence vocale, vidéo et de collaboration.
    
      - **Conférences**   cette sélection permet d’obtenir une gamme étendue de fonctionnalités, notamment:
        
          - Messagerie instantanée avec plus de deux parties dans une session de messagerie instantanée.
        
          - Conférences, qui comprennent la collaboration sur des documents, le partage d’application et le partage de bureau.
        
          - Une conférence a/V, qui permet aux utilisateurs d’effectuer des conférences audio/vidéo (A/V) en temps réel sans recourir à des services externes tels que le service Live Meeting ou un pont audio tiers.
    
      - **Les conférences**   rendez-vous (RTC) permettent aux utilisateurs d’accéder à la partie audio d’une conférence 2013 Server Lync à l’aide d’un téléphone réseau téléphonique commuté (PSTN) sans nécessiter un fournisseur de services d’audioconférence.
    
      - **Enterprise voix**   entreprise voix est la solution VoIP (Voice over IP) dans Lync Server 2013, qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques. Vous déploierez cette fonctionnalité si vous envisagez d’utiliser Lync Server 2013 pour les appels vocaux, la messagerie vocale et d’autres fonctions qui utilisent un appareil matériel ou un client logiciel.
    
      - **Le contrôle d’admission des appels (CAC)**   CAC détermine, en fonction de la bande passante disponible sur le réseau, s’il est possible d’établir des sessions de communication en temps réel telles que des appels vocaux ou vidéo. Si vous avez déployé uniquement la messagerie instantanée et la présence, CAC n’est pas nécessaire, car aucune de ces deux fonctionnalités n’utilise le CAC.
    
      - **** L’archivage de l’archivage vous permet d’archiver le contenu du message instantané, le contenu de la réunion ou les deux envoyés via Lync Server 2013.   
    
      - **La surveillance**   de Analysis Server vous permet de recueillir des données numériques qui décrivent la qualité multimédia sur votre réseau et vos points de terminaison, des informations sur l’utilisation des appels VoIP, des messages instantanés, des conversations par messagerie instantanée, des réunions, du partage d’applications et du fichier. transferts et informations d’erreur et de dépannage pour les appels en échec.
    
    <div>
    

    > [!NOTE]
    > Si vous voulez activer le CAC dans votre déploiement, il est nécessaire d’activer le service CAC dans exactement un pool par site central. Le CAC est recommandé si vous déployez des fonctions vocales ou des conférences A/V.

    
    </div>
    
    Le tableau suivant répertorie les fonctionnalités disponibles (haut) et les fonctions proposées aux utilisateurs (à gauche). Les sélections du tableau sont celles que vous devez sélectionner pour activer ces fonctionnalités pour votre organisation.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Conférence</th>
    <th>Conférence rendez-vous</th>
    <th>Voix Entreprise</th>
    <th>Contrôle d’admission des appels</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Messagerie instantanée et présence</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Conférence</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>Conférence A/V</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Voix Entreprise</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Dans la page **Sélectionner des rôles de serveur** colocalisés, vous pouvez Collocate le serveur de médiation sur le serveur frontal ou le déployer en tant que serveur autonome.
    
    Vous pouvez collocate le serveur de médiation sur le pool frontal.
    
      - Si vous envisagez de collocate le serveur de médiation sur le pool frontal Enterprise Edition, assurez-vous que la case à cocher est activée. Le rôle serveur sera déployé sur les serveurs du pool.
    
      - Si vous envisagez de déployer le serveur de médiation en tant que serveur autonome, décochez la case correspondante. Vous déploierez le serveur de médiation dans une étape de déploiement séparée après le déploiement complet du serveur frontal.
    
    <div>
    

    > [!NOTE]
    > Nous vous recommandons de collocate le serveur de médiation, le cas échéant. Pour plus d’informations sur la prise en charge des serveurs de médiation autonomes ou autonomes, voir <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">composants et topologies du serveur de médiation dans Lync Server 2013</A> dans la documentation de planification.

    
    </div>

6.  Les **rôles serveur Associate avec cette page de pool frontal** vous permettent de définir et d’associer des rôles de serveur avec le pool frontal. Le rôle suivant est disponible :
    
    **Activer un pool**   Edge définit et associe un serveur Edge unique ou un pool de serveurs Edge. Un serveur Edge facilite la communication et la collaboration entre les utilisateurs au sein de l’organisation et les personnes qui travaillent en dehors de celle-ci, notamment les utilisateurs fédérés.
    
    Vous pouvez utiliser deux scénarios possibles pour déployer et associer les rôles de serveur:
    
    Dans le premier scénario, vous définissez une nouvelle topologie pour une nouvelle installation. Vous pouvez aborder l’installation de deux manières:
    
      - Laissez la case à cocher désactivée et continuez de définir la topologie. Une fois les rôles serveur frontal et principal publiés, configurés et testés, vous pouvez réexécuter le Générateur de topologies afin de les ajouter à la topologie. Cette stratégie vous permet de tester le pool frontal et le serveur exécutant SQL Server sans complications supplémentaires provenant de rôles supplémentaires. Une fois les tests initiaux réalisés, vous pouvez réexécuter le Générateur de topologies afin de sélectionner les rôles à déployer.
    
      - Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.
    
    Dans le scénario 2, vous disposez d’un déploiement existant et votre infrastructure est prête pour de nouveaux rôles ou vous devez associer des rôles existants à un nouveau serveur frontal:
    
      - Dans ce cas, vous devez sélectionner les rôles que vous souhaitez déployer ou associer au nouveau serveur frontal. Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.

7.  Dans la page **définir le SQL Store** , effectuez l’une des opérations suivantes:
    
      - Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL**.
    
      - Pour définir une nouvelle instance SQL Server pour stocker des informations de pool, cliquez sur **nouveau** , puis spécifiez le **nom de domaine complet SQL Server**dans la boîte de dialogue **définir un nouveau SQL Store** .
    
      - Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée**, puis spécifiez le nom de l’instance.
    
      - Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut**.
    
      - Pour utiliser la mise en miroir SQL, sélectionnez **activer la mise en miroir SQL** et sélectionnez une instance existante ou créez une nouvelle instance.

8.  Dans la page **définir le partage de fichiers** , effectuez l’une des opérations suivantes:
    
      - Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini**.
    
      - Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers**. Dans la zone **Nom de domaine complet du serveur de fichiers**, entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers**.
    
    <div>
    

    > [!IMPORTANT]
    > Le partage de fichiers pour Lync Server 2013 ne se trouve pas sur le serveur frontal. Notez que dans cet exemple, le partage de fichiers a été localisé sur le serveur principal SQL Server. Il est possible qu’il ne s’agit pas d’un emplacement optimal pour les besoins de votre organisation, et qu’un serveur de fichiers soit un meilleur choix. Vous pouvez définir le partage de fichiers sans avoir à le créer. Vous devrez créer le partage de fichiers à l’emplacement défini avant de publier la topologie.

    
    </div>

9.  Dans la page **spécifier l’URL du service Web** , effectuez l’une des opérations suivantes ou les deux:
    
    <div>
    

    > [!IMPORTANT]
    > L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Si vous avez plusieurs pools frontal ou serveur principal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.

    
    </div>
    
    1.  Si vous configurez l’équilibrage de charge DNS, activez la case à cocher **remplacer le FQDN du pool de services Web interne** , entrez l’URL de base interne (qui doit être différente de celle du pool de nom\<de domaine complet\>, par exemple, l’URL de base) dans ** URL de base interne**.
        
        <div>
        

        > [!WARNING]
        > Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de directeurs. <STRONG>Utilisez uniquement les caractères standard</STRONG> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous définissez les URL ou les noms de domaine complets. N’utilisez pas les caractères ou traits de soulignement Unicode. Souvent, les caractères non standard dans une URL ou un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand l’URL ou le FQDN doit être assigné au nom ou à l’autre nom de l’objet dans le certificat).

        
        </div>
    
    2.  Si vous le souhaitez, entrez l’URL de base externe dans **URL de base externe**. Pour différencier votre nom de domaine interne, entrez l’URL de base externe. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous devez définir l’URL en utilisant le nom de domaine contoso.com. Cela est également important dans le cas d’un proxy inverse. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.
    
    <div>
    

    > [!NOTE]
    > Pour utiliser l’équilibrage de charge DNS, vous devez créer les enregistrements DNS appropriés. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurer le DNS pour l’équilibrage de charge dans Lync Server 2013</A>.

    
    </div>

10. Si vous avez sélectionné l’option **conférences** dans la page **Sélectionner des fonctionnalités** , dans la page **Sélectionner un serveur Office Web Apps** , sélectionnez **associer le pool à un serveur Office Web Apps** , puis cliquez sur **nouveau** (ou sélectionnez une application Office Web Apps existante). Serveur dans la liste déroulante).

11. Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
    Si Office Web Apps Server est installé en local et dans la même zone réseau que Lync Server 2013, l’option **Office Web Apps Server déployée sur un réseau externe (c’est-à-dire le périmètre/Internet)** ne doit pas être sélectionnée.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configuration de l’intégration avec Office Web Apps Server et Lync Server 2013</A>.

    
    </div>

12. Dans la page **définir le SQL Store** d’archivage, sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour stocker les données associées aux données d’archivage.

13. Dans la page **définir la surveillance du SQL Store** , sélectionnez une instance existante ou SQL Server, ou définissez une nouvelle instance pour le stockage des données associées aux données d’analyse.

14. Cliquez sur **Suivant**. Si vous avez défini d’autres serveurs de rôles sur la page **associer des rôles de serveur à cette liste frontale** , des pages d’assistant de configuration de rôles distinctes s’ouvrent pour vous permettre de configurer les rôles de serveur. Pour plus d’informations, reportez-vous aux rubriques suivantes:
    
    [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Si vous n’avez pas sélectionné de rôles serveur supplémentaires à configurer et déployer ou lorsque vous avez terminé la configuration des serveurs de rôles supplémentaires, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

