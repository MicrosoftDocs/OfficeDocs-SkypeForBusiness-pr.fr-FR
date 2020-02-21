---
title: Demander et configurer un certificat pour votre proxy HTTP inverse
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5db6e8ed2df53acf5c1543569778b29168d0500b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Demander et configurer un certificat pour votre proxy HTTP inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-14_

Vous devez installer le certificat de l’autorité de certification (CA) racine sur le serveur exécutant Microsoft Forefront Threat Management Gateway 2010 ou IIS ARR pour l’infrastructure de l’autorité de certification qui a émis les certificats de serveur sur les serveurs internes exécutant Microsoft Lync. Serveur 2013.

Vous devez également installer un certificat de serveur web public sur votre serveur proxy inverse. Les autres noms de sujet de ce certificat doivent contenir les noms de domaine complets externes publiés de chaque pool hébergeant les utilisateurs activés pour l’accès à distance, ainsi que les noms de domaine complets externes de tous les directeurs ou pools directeurs qui seront utilisés dans cette infrastructure Edge. L’autre nom de sujet doit aussi contenir l’URL simple de réunion, l’URL simple de conférence rendez-vous et, si vous déployez des applications mobiles et prévoyez d’utiliser la découverte automatique, l’URL du service de découverte automatique externe, comme indiqué dans le tableau suivant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Valeur</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom du sujet</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Autre nom du sujet</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> Le nom du sujet doit aussi être présent dans l’autre nom de sujet.

</td>
</tr>
<tr class="odd">
<td><p>Autre nom du sujet</p></td>
<td><p>Services Web de directeur facultatifs (si Director est déployé)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Autre nom du sujet</p></td>
<td><p>URL simple de réunion</p>



> [!NOTE]
> Toutes les URL simples de réunion doivent se trouver dans l’autre nom de sujet. Chaque domaine SIP doit comporter au moins une URL simple de réunion active.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Autre nom du sujet</p></td>
<td><p>URL simple Dial-in</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Autre nom du sujet</p></td>
<td><p>Office Web Apps Server</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Autre nom du sujet</p></td>
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Si vous utilisez également Microsoft Exchange Server, vous devrez également configurer des règles de proxy inverse pour les URL de services Web et de découverte automatique Exchange.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Si votre déploiement interne se compose de plusieurs serveurs Standard Edition ou pools frontaux, vous devez configurer les règles de publication web pour chaque nom de domaine complet (FQDN) externe de la batterie de serveurs web. En outre, soit vous avez besoin d’un certificat et d’un port d’écoute web pour chacun, soit vous devez obtenir un certificat dont l’autre nom de sujet contient les noms utilisés par tous les pools, l’affecter à un port d’écoute web et le partager entre plusieurs règles de publication web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Créer une demande de certificat

Vous créez une demande de certificat sur le proxy inverse. Vous créez une demande sur un autre ordinateur, mais vous devez exporter le certificat signé avec la clé privée et l’importer sur le proxy inverse une fois que vous l’avez reçu de l’autorité de certification publique.

<div>


> [!NOTE]
> Une demande de certificat ou une demande de signature de certificat (CSR) est une demande adressée à une autorité de certification publique (CA) approuvée pour valider et signer la clé publique de l’ordinateur demandeur. Lorsqu’un certificat est généré, une clé publique et une clé privée sont créées. Seule la clé publique est partagée et signée. Comme son nom l’indique, la clé publique est mise à la disposition de toute demande publique. La clé publique est destinée à être utilisée par les clients, les serveurs et d’autres demandeurs qui doivent échanger des informations en toute sécurité et valider l’identité d’un ordinateur. La clé privée est gardée sécurisée et n’est utilisée que par l’ordinateur qui a créé la paire de clés pour déchiffrer les messages chiffrés avec sa clé publique. La clé privée peut être utilisée à d’autres fins. Pour les rôles de proxy inverse, le chiffrement des données est l’utilisation principale. Accessoire, l’authentification par certificat au niveau de la clé de certificat est une autre utilisation et est limitée uniquement à la validation qu’un demandeur a la clé publique de l’ordinateur, ou que l’ordinateur pour lequel vous avez une clé publique est effectivement l’ordinateur qu’il prétend être.



</div>

<div>


> [!TIP]
> Si vous planifiez les certificats de votre serveur Edge et vos certificats de proxy inverse en même temps, vous devez remarquer qu’il existe beaucoup de similitudes entre les deux exigences de certificat. Lorsque vous configurez et demandez votre certificat de serveur Edge, combinez le serveur Edge et les autres noms de sujet de proxy inverse. Vous pouvez utiliser le même certificat pour votre proxy inverse si vous exportez le certificat et la clé privée, puis copiez le fichier exporté vers le proxy inverse, puis importez le certificat/la paire de clés et attribuez-le selon vos besoins dans les procédures à venir. Reportez-vous à la rubrique Certificate Requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">plan for Edge Server Certificates in Lync Server 2013</A> et The inversion proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate Summary-Reverse Proxy in Lync Server 2013</A>. Veillez à créer le certificat avec une clé privée exportable. La création du certificat et de la demande de certificat avec une clé privée exportable est requise pour les serveurs Edge regroupés, c’est une pratique normale et l’Assistant certificat de l’Assistant Déploiement de Lync Server pour le serveur Edge vous permet de définir l’indicateur <STRONG>Make Private Key exportable</STRONG> . Une fois que vous avez reçu la demande de certificat de l’autorité de certification publique, vous exportez le certificat et la clé privée. Reportez-vous à la section « pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool » dans la rubrique <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">set up Certificates for the external Edge interface for Lync Server 2013</A> pour plus d’informations sur la procédure de création et d’exportation de votre certificat avec une clé privée. L’extension du certificat doit être de type <STRONG>. pfx</STRONG>.



</div>

Pour générer une demande de signature de certificat sur l’ordinateur sur lequel le certificat et la clé privée seront affectés, procédez comme suit :

**Création d’une demande de signature de certificat**

1.  Ouvrez la console MMC (Microsoft Management Console) et ajoutez le composant logiciel enfichable Certificats, sélectionnez **ordinateurs**, puis développez **personnel**. Pour plus d’informations sur la création d’une console certificats dans la console MMC (Microsoft Management Console [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)), reportez-vous à la rubrique.

2.  Cliquez avec le bouton droit sur **certificats**, cliquez sur **toutes les tâches**, puis sur **opérations avancées**, cliquez sur **créer une demande personnalisée**.

3.  Dans la page d' **enregistrement du certificat** , cliquez sur **suivant**.

4.  Dans la page **Sélectionner une stratégie d’enregistrement de certificat** sous **demande personnalisée**, sélectionnez **continuer sans la stratégie d’enregistrement**. Cliquez sur **Suivant**.

5.  Sur la page **demande personnalisée** , pour la clé héritée de sélection de **modèle** **(aucun modèle)**. Sauf indication contraire de votre fournisseur de certificats, laissez la case à cocher **Supprimer les extensions par défaut** désactivée et la sélection **format de demande** sur ** \#PKCS 10**. Cliquez sur **Suivant**.

6.  Sur la page informations sur le **certificat** , cliquez sur **Détails**, puis sur **Propriétés**.

7.  Dans la page **Propriétés du certificat** , sous l’onglet **général** , dans le champ **nom convivial** , tapez un nom pour ce certificat. Si vous le souhaitez, tapez une description dans le champ **Description** . Le nom convivial et la description sont généralement utilisés par l’administrateur pour identifier l’objectif du certificat, par exemple l' **écouteur de proxy inverse pour Lync Server**.

8.  Sélectionnez l’onglet **sujet** . Sous **nom du sujet** pour le **type**, sélectionnez **nom commun** pour le type de nom d’objet. Pour la **valeur**, tapez le nom de l’objet que vous allez utiliser pour le proxy inverse, puis cliquez sur **Ajouter**. Dans l’exemple fourni dans le tableau de cette rubrique, le nom de l’objet est webext.contoso.com et sera tapé dans le champ de valeur du nom de l’objet.

9.  Sous **autre nom**, dans l’onglet **objet** , sélectionnez **DNS** dans la liste déroulante pour **type**. Pour chaque autre nom de sujet défini dont vous avez besoin sur le certificat, tapez le nom de domaine complet, puis cliquez sur **Ajouter**. Par exemple, dans le tableau, il existe trois autres noms de sujet, meet.contoso.com, dialin.contoso.com et lyncdiscover.contoso.com. Dans le champ **valeur** , tapez Meet.contoso.com, puis cliquez sur **Ajouter**. Répétez l’opération pour chaque autre nom de sujet que vous devez définir.

10. Sur la page **Propriétés du certificat** , cliquez sur l’onglet **Extensions** . Sur cette page, vous allez définir les rôles de clé de chiffrement dans l' **utilisation** de la clé et l’utilisation de la clé étendue dans **l’utilisation étendue de la clé (stratégies d’application)**.

11. Cliquez sur la flèche d' **utilisation clé** pour afficher les **options disponibles**. Sous options disponibles, cliquez sur **signature numérique**, puis sur **Ajouter**. Cliquez sur **chiffrement**de la clé, puis sur **Ajouter**. Si la case à cocher **appliquer ces utilisations de clés critiques** n’est pas cochée, activez la case à cocher.

12. Cliquez sur la flèche utilisation de la **clé étendue (stratégies d’application)** pour afficher les **options disponibles**. Sous options disponibles, cliquez sur **authentification serveur**, puis sur **Ajouter**. Cliquez sur **authentification client**, puis sur **Ajouter**. Si la case à cocher **activer les utilisations de la clé étendue critique** est activée, désélectionnez la case à cocher. Contrairement à la case à cocher utilisation de la clé (qui doit être vérifiée), vous devez vous assurer que la case à cocher utilisation étendue de la clé n’est pas activée.

13. Sur la page **Propriétés du certificat** , cliquez sur l’onglet **clé privée** . **** Pour **taille**de la clé, sélectionnez **2048** dans la liste déroulante. Si vous générez ce couple de clés et CSR sur un ordinateur autre que le proxy inverse auquel ce certificat est destiné, sélectionnez **définir la clé privée exportable**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" />Note de sécurité :</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>La sélection d' <strong>une clé privée exportable</strong> est généralement conseillée lorsque vous avez plusieurs proxys inverses dans une batterie de serveurs, car vous copiez le certificat et la clé privée sur chaque ordinateur de la batterie de serveurs. Si vous autorisez une clé privée exportable, vous devez vous préoccuper du certificat et de l’ordinateur sur lequel il est généré. La clé privée, si elle est compromise, rend le certificat inutile et expose potentiellement l’ordinateur ou les ordinateurs à l’accès externe et aux autres failles de sécurité.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Sous l’onglet **clé privée** , cliquez sur la flèche **type de touche** . Sélectionnez l’option **Exchange** .

15. Cliquez sur **OK** pour enregistrer les **Propriétés de certificat** que vous avez définies.

16. Dans la page d' **enregistrement du certificat** , cliquez sur **suivant**.

17. Sur la page **où voulez-vous enregistrer la demande hors connexion ?** , vous êtes invité à indiquer un **nom de fichier** et un **format de fichier** pour l’enregistrement de la demande de signature de certificat.

18. Dans le champ **nom de fichier** , tapez le chemin d’accès et le nom de fichier de la demande, ou cliquez sur **Parcourir** pour sélectionner un emplacement pour le fichier et tapez le nom de fichier de la demande.

19. Pour **format de fichier**, cliquez sur **base 64** ou **binaire**. Sélectionnez **Base 64** , sauf si vous y êtes invité autrement par le fournisseur pour vos certificats.

20. Recherchez le fichier de demande que vous avez enregistré à l’étape précédente. Envoyez-le à votre autorité de certification publique.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft a identifié des autorités de certification publiques qui répondent aux exigences des communications unifiées. Une liste est conservée dans l’article suivant de la base de connaissances. <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

