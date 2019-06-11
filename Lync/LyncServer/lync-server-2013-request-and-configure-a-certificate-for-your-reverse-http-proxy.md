---
title: Demande et configuration d’un certificat pour votre proxy HTTP inverse
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Demande et configuration d’un certificat pour votre proxy HTTP inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-14_

Vous avez besoin d’installer le certificat d’autorité de certification racine sur le serveur exécutant la passerelle 2010 ou les services IIS ARR pour l’infrastructure de l’autorité de certification qui a émis les certificats serveur sur les serveurs internes exécutant Microsoft Lync Server 2013.

Vous devez également installer un certificat de serveur Web public sur votre serveur proxy inverse. Le nom d’une autre personne doit contenir le nom de domaine complet (FQDN) publié de chaque liste de tous les utilisateurs autorisés à accéder à distance et les noms de domaine complets externes de tous les directeurs ou pools de réalisateurs qui seront utilisés dans Cette infrastructure latérale. Le nom de remplacement de l’objet doit également contenir l’URL simple de la réunion, l’URL d’accès à la Conférence rendez-vous et, si vous déployez des applications mobiles et vous envisagez d’utiliser la découverte automatique, comme indiqué dans le tableau suivant.


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
<td><p>Nom de l’objet</p></td>
<td><p>FQDN du pool</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Autre nom du sujet</p></td>
<td><p>FQDN du pool</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> Le nom du sujet doit également figurer dans l’autre nom de l’objet.

</td>
</tr>
<tr class="odd">
<td><p>Autre nom du sujet</p></td>
<td><p>Services Web de Director facultatifs (si le directeur est déployé)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Autre nom du sujet</p></td>
<td><p>URL simple pour la réunion</p>



> [!NOTE]
> Toutes les URL simples de la réunion doivent figurer dans le nom de l’autre objet. Chaque domaine SIP doit avoir au moins une URL simple pour la réunion active.

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
> Si vous utilisez également Microsoft Exchange Server, vous devez également configurer les règles de proxy inverse pour les URL de découverte automatique et de services Web Exchange.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Si votre déploiement interne se compose de plus d’un serveur Standard Edition ou d’une liste frontale, vous devez configurer les règles de publication Web pour chaque nom de domaine complet de la batterie de serveurs Web externe, ou vous devez disposer d’un certificat et d’un écouteur Web pour chacun d’eux ou vous devez obtenir un certificat. dont le nom de remplacement de l’objet contient les noms utilisés par tous les pools, attribuez-le à un écouteur Web et partagez-le entre plusieurs règles de publication Web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Créer une demande de certificat

Vous créez une demande de certificat sur le proxy inverse. Vous créez une demande sur un autre ordinateur, mais vous devez exporter le certificat signé avec la clé privée et l’importer sur le proxy inverse une fois que vous l’avez reçu de l’autorité de certification publique.

<div>


> [!NOTE]
> Une demande de certificat ou une demande de signature de certificat (CSR) est une demande adressée à une autorité de certification publique de confiance (CA) pour valider et signer la clé publique de l’ordinateur à la demande. Une clé publique et une clé privée sont créées lors de la génération d’un certificat. Seule la clé publique est partagée et signée. Comme son nom l’indique, la clé publique est mise à la disposition d’une requête publique. La clé publique est utilisée par les clients, serveurs et autres demandeurs qui doivent échanger des informations en toute sécurité et valider l’identité d’un ordinateur. La clé privée reste sécurisée et est utilisée uniquement par l’ordinateur qui a créé la paire de clés pour déchiffrer les messages chiffrés avec sa clé publique. La clé privée peut être utilisée à d’autres fins. Pour les fins de proxy inverse, le chiffrement des données est l’utilisation principale. Par le biais de l’authentification par certificat sur le niveau clé du certificat, l’authentification par certificat est une autre utilisation et est limitée uniquement à la validation qu’un demandeur possède la clé publique de l’ordinateur ou que l’ordinateur sur lequel vous avez une clé publique est réellement l’ordinateur qu’il prétend être.



</div>

<div>


> [!TIP]
> Si vous planifiez des certificats de serveur Edge et vos certificats de proxy inverse en même temps, vous remarquerez qu’il existe de nombreuses similitudes entre les deux exigences de certificat. Lorsque vous configurez et demandez votre certificat de serveur Edge, combinez le serveur Edge et les noms de remplacement de l’objet proxy inverse. Vous pouvez utiliser le même certificat pour votre proxy inverse si vous exportez le certificat et la clé privée, puis copiez le fichier exporté sur le proxy inverse, puis importez le certificat/paire de clés et attribuez-le selon les besoins dans les prochaines procédures. Consultez la configuration requise pour les certificats pour le&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">plan de serveur Edge pour les certificats de serveur de périmètre dans Lync Server 2013</A> et la synthèse des certificats de proxy inverse <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy sur Lync Server 2013</A>. Veillez à créer le certificat à l’aide d’une clé privée exportable. La création du certificat et de la demande de certificat à l’aide d’une clé privée exportable est requise pour les serveurs Edge en pool, donc il s’agit d’une pratique normale et l’Assistant certificat dans l’Assistant Déploiement de Lync Server pour le serveur Edge vous permet de définir le mode de création <STRONG> indicateur d’exportation de clé privée</STRONG> . Lorsque vous recevez à nouveau la demande de certificat de l’autorité de certification publique, vous exportez le certificat et la clé privée. Pour plus d’informations sur la façon de créer et exporter votre certificat à l’aide d’une clé privée, voir la section «pour exporter le certificat avec la clé privée pour <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">2013 les</A> serveurs Edge dans un pool». L’extension du certificat doit être de type <STRONG>. pfx</STRONG>.



</div>

Pour générer une demande de signature de certificat sur l’ordinateur où le certificat et la clé privée seront attribués, procédez comme suit:

**Création d’une demande de signature de certificat**

1.  Ouvrez Microsoft Management Console (MMC), ajoutez le composant logiciel enfichable Certificats et sélectionnez **ordinateurs**, puis développez **personnel**. Pour plus d’informations sur la création d’une console de certificats dans Microsoft Management Console (MMC) [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616), voir.

2.  Cliquez avec le bouton droit sur **certificats**, cliquez sur **toutes les tâches**, cliquez sur **opérations avancées**, cliquez sur **créer une requête personnalisée**.

3.  Dans la page **inscription du certificat** , cliquez sur **suivant**.

4.  Dans la page **Sélectionner une stratégie d’inscription de certificat** sous **demande personnalisée**, sélectionnez **continuer sans stratégie d’inscription**. Cliquez sur **Suivant**.

5.  Dans la page de **demande personnalisée** , pour le **modèle** , sélectionnez **(sans modèle) clé héritée**. Si ce n’est pas le cas, laissez la case à cocher **Supprimer les extensions par défaut** activée et sélectionnez format de la **requête** dans ** \#PKCS 10**. Cliquez sur **Suivant**.

6.  Dans la page informations sur le **certificat** , cliquez sur **Détails**, puis cliquez sur **Propriétés**.

7.  Dans la page **Propriétés du certificat** sous l’onglet **général** , dans le champ **nom convivial** , tapez le nom de ce certificat. Vous pouvez également taper une description dans le champ **Description** . Le nom convivial et la description sont généralement utilisés par l’administrateur pour identifier l’objet du certificat, par exemple l' **écouteur de proxy inverse de Lync Server**.

8.  Sélectionnez l’onglet **objet** . Sous **nom du sujet** du **type**, sélectionnez **nom usuel** pour le type de nom de sujet. Pour la **valeur**, tapez le nom du sujet que vous allez utiliser pour le proxy inverse, puis cliquez sur **Ajouter**. Dans l’exemple fourni dans le tableau figurant dans cette rubrique, le nom du sujet est webext.contoso.com et sera tapé dans le champ Value du nom du sujet.

9.  Dans l’onglet **objet** sous **nom alternatif**, sélectionnez **DNS** dans la liste déroulante pour **type**. Pour chaque nom de remplacement défini d’objet requis sur le certificat, tapez le nom de domaine complet, puis cliquez sur **Ajouter**. Par exemple, dans le tableau figure trois autres noms d’objet, meet.contoso.com, dialin.contoso.com et lyncdiscover.contoso.com. Dans le champ **valeur** , tapez Meet.contoso.com, puis cliquez sur **Ajouter**. Répétez l’opération pour chaque nom alternatif que vous devez définir.

10. Dans la page **Propriétés du certificat** , cliquez sur l’onglet **Extensions** . Dans cette page, vous allez définir les rôles de clé de **** chiffrement lors de l’utilisation de la clé et de l’utilisation de la clé étendue dans l’utilisation de la **clé étendue (stratégies d’application)**.

11. Cliquez sur la flèche **utilisation des touches** pour afficher les **options disponibles**. Sous options disponibles, cliquez sur **signature numérique**, puis cliquez sur **Ajouter**. Cliquez sur **chiffrage de clés**, puis cliquez sur **Ajouter**. Si les cases à cocher **rendre ces utilisations** de la clé sont essentielles ne sont pas activées, activez la case à cocher.

12. Cliquez sur la flèche utilisation de la **touche étendue (stratégies d’application)** pour afficher les **options disponibles**. Sous options disponibles, cliquez sur **authentification du serveur**, puis cliquez sur **Ajouter**. Cliquez sur **authentification du client**, puis cliquez sur **Ajouter**. Si vous activez la case à cocher **activer l’utilisation des touches étendues** , décochez la case. Contrairement à la case à cocher utilisation de la clé (qui doit être activée), vous devez vous assurer que la case à cocher utilisation de la clé étendue n’est pas activée.

13. Dans la page **Propriétés du certificat** , cliquez sur la flèche en regard de **** l’onglet **clé privée** . Pour la taille de la **clé**, sélectionnez **2048** dans la liste déroulante. Si vous générez cette paire de clés et votre CSR sur un ordinateur autre que le proxy inverse auquel ce certificat est destiné, sélectionnez **rendre la clé privée**exportable.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" />Note de sécurité:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Il est généralement conseillé de sélectionner l’option <strong>rendre une clé privée</strong> exportée lorsque vous avez plusieurs proxys inversés dans une batterie de serveurs, car vous copiez le certificat et la clé privée vers chaque ordinateur dans la batterie de serveurs. Si vous autorisez une clé privée exportable, vous devez veiller à ce que le certificat et l’ordinateur sur lesquels il est généré. La clé privée, si celle-ci est compromise, génère le certificat de manière inutilisable et risque d’exposer le ou les ordinateurs à des failles de sécurité.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Dans l’onglet **clé privée** , cliquez sur la flèche **type de clé** . Sélectionnez l’option **Exchange** .

15. Cliquez sur **OK** pour enregistrer les **Propriétés de certificat** que vous avez définies.

16. Dans la page **inscription du certificat** , cliquez sur **suivant**.

17. Sur la page **où voulez-vous enregistrer la demande hors connexion?** , vous êtes invité à entrer un **nom de fichier** et un **format de fichier** pour enregistrer la demande de signature de certificat.

18. Dans le champ de saisie du **nom de fichier** , tapez le chemin d’accès et le nom de fichier de la demande, ou cliquez sur **Parcourir** pour sélectionner un emplacement pour le fichier, puis tapez le nom de fichier de la requête.

19. Pour le **format de fichier**, cliquez sur **base 64** ou **binaire**. Sélectionnez **Base 64** , à moins que vous ne soyez invité par le fournisseur pour vos certificats.

20. Recherchez le fichier de demande que vous avez enregistré à l’étape précédente. Envoyez-la à votre autorité de certification publique.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft a identifié les autorités de certification publiques qui répondent à vos besoins en matière de communications unifiées. Une liste est conservée dans l’article de la base de connaissances suivant. <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

