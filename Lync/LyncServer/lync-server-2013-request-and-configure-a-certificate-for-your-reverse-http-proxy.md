---
title: "Lync Server 2013 : Demande et conf. d’un certif. pour votre proxy HTTP inverse"
TOCTitle: Demande et configuration d’un certificat pour votre proxy HTTP inverse
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429704(v=OCS.15)
ms:contentKeyID: 49297146
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Demande et configuration d’un certificat pour votre proxy HTTP inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous devez installer le certificat d’autorité de certification (CA) racine sur le serveur qui exécute Microsoft Forefront Threat Management Gateway 2010 ou IIS ARR pour l’infrastructure CA qui a émis les certificats de serveur sur les serveurs internes exécutant Microsoft Lync Server 2013.

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
<div>

> [!IMPORTANT]  
> Le nom du sujet doit aussi être présent dans l’autre nom de sujet.
</div></td>
</tr>
<tr class="odd">
<td><p>Autre nom du sujet</p></td>
<td><p>Services web directeur facultatifs (si directeur est déployé)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Autre nom du sujet</p></td>
<td><p>URL simple de réunion</p>
<div>

> [!NOTE]  
> Toutes les URL simples de réunion doivent se trouver dans l’autre nom de sujet. Chaque domaine SIP doit comporter au moins une URL simple de réunion active.
</div></td>
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
<div>

> [!NOTE]  
> Si vous utilisez Microsoft Exchange Server, vous devrez également configurer les règles de proxy inverse pour les URL de découverte automatique Exchange et des services web.
</div></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Si votre déploiement interne se compose de plusieurs serveurs Standard Edition ou pools frontaux, vous devez configurer les règles de publication web pour chaque nom de domaine complet (FQDN) externe de la batterie de serveurs web. En outre, soit vous avez besoin d’un certificat et d’un port d’écoute web pour chacun, soit vous devez obtenir un certificat dont l’autre nom de sujet contient les noms utilisés par tous les pools, l’affecter à un port d’écoute web et le partager entre plusieurs règles de publication web.

## Créer une demande de certificat

Une demande de certificat est créée sur le proxy inverse. Si vous créez une demande sur un autre ordinateur, vous devez tout de même exporter le certificat signé avec la clé privée, puis l’importer sur le proxy inverse une fois que vous l’avez reçu de l’autorité de certification publique.

> [!NOTE]  
> Une demande de certificat ou une demande de signature de certificat (CSR) est adressée à une autorité de certification publique approuvée afin de valider et signer la clé publique de l’ordinateur à l’origine de la demande. Lorsqu’un certificat est généré, une clé publique et une clé privée sont créées. Seule la clé publique est partagée et signée. Comme son nom l’indique, la clé publique est mise à disposition pour toute demande publique. La clé publique est destinée à l’usage des clients, serveurs et autres demandeurs devant échanger des informations de façon sécurisée et valider l’identité d’un ordinateur. La clé privée est conservée de façon sécurisée et utilisée uniquement par l’ordinateur ayant créé la paire de clés pour déchiffrer les messages chiffrés avec sa clé publique. La clé privée peut être utilisée à d’autres fins. Le chiffrement des données constitue la principale utilisation pour le proxy inverse. L’authentification du certificat au niveau de la clé de certificat constitue une autre utilisation. Celle-ci cherche à vérifier que le demandeur dispose de la clé publique de l’ordinateur ou que l’ordinateur pour lequel vous avez une clé publique est réellement l’ordinateur qu’il prétend être.

> [!TIP]  
> Si vous planifiez vos certificats de serveur Edge et de proxy inverse simultanément, vous remarquerez certainement qu’ils y a de grandes similitudes entre leurs exigences. Lorsque vous configurez et demandez votre certificat de serveur Edge, vous devez combiner les autres noms de sujet du serveur Edge et du proxy inverse. Vous pouvez utiliser le même certificat pour votre proxy inverse si vous exportez le certificat et la clé privée, copiez le fichier exporté vers le proxy inverse, importez la paire certificat/clé, puis affectez celle-ci de façon appropriée dans les procédures suivantes. Consultez les exigences de certificat de serveur Edge ( <a href="lync-server-2013-plan-for-edge-server-certificates.md">Planification des certificats de serveur Edge dans Lync Server 2013</a>) et de proxy inverse ( <a href="lync-server-2013-certificate-summary-reverse-proxy.md">Résumé des certificats - Proxy inverse dans Lync Server 2013</a>). Veillez à créer le certificat avec une clé privée exportable. La création du certificat et de la demande de certificat avec une clé de ce type est nécessaire pour les serveurs Edge regroupés, aussi s’agit-il d’une pratique normale. L’Assistant Certificat dans l?’Assistant Déploiement de Lync Server pour le serveur Edge vous permet d’ailleurs de définir l’indicateur <strong>Permettre l’exportation de la clé privée</strong> . Lorsque vous recevez la demande de certificat de l’autorité de certification publique, vous devez exporter le certificat et la clé privée. Pour plus d’informations sur la création et l’exportation de votre certificat avec une clé privée, reportez-vous à la section « Pour exporter le certificat avec la clé privée pour les serveurs Edge d’un pool » de la rubrique <a href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Configuration des certificats pour l’interface Edge externe pour Lync Server 2013</a>. L’extension du certificat doit être de type <strong>.pfx</strong>.

Pour générer une demande de signature de certificat sur l’ordinateur sur lequel le certificat et la clé privée seront affectés, procédez comme suit :

**Création d’une demande de signature de certificat**

1.  Ouvrez la Microsoft Management Console (MMC), ajoutez le composant logiciel enfichable Certificats, sélectionnez **Ordinateurs** , puis développez **Personnel** . Pour plus d’informations sur la création de certificats dans la Microsoft Management Console (MMC), reportez-vous à [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).

2.  Cliquez avec le bouton droit sur **Certificats** , cliquez sur **Toutes les tâches** , **Opérations avancées** , puis sur **Créer une demande personnalisée** .

3.  Dans la page **Inscription de certificats** , cliquez sur **Suivant** .

4.  Dans la page **Sélectionner la stratégie d’inscription de certificat** sous **Demande personnalisée** , sélectionnez **Continuer sans stratégie d’inscription** . Cliquez sur **Suivant** .

5.  Dans la page **Demande personnalisée** , pour **Modèle** , sélectionnez **(Aucun modèle) Clé héritée** . Sauf instruction contraire de votre fournisseur de certificats, laissez l’option **Supprimer les extensions par défaut** désactivée et l’option **Format de la demande** définie sur **PKCS \#10** . Cliquez sur **Suivant** .

6.  Dans la page **Informations sur le certificat** , cliquez sur **Détails** , puis sur **Propriétés** .

7.  Dans la page **Propriétés du certificat** sous l’onglet **Général** dans le champ **Nom convivial** , tapez le nom du certificat. Vous pouvez éventuellement taper une description dans le champ **Description** . Le nom convivial et la description sont généralement utilisés par l’Administrateur pour identifier l’objet du certificat (par exemple, **Écouteur de proxy inverse pour Lync Server**).

8.  Sélectionnez l’onglet **Sujet** . Sous **Nom du sujet** , pour **Type** , sélectionnez **Nom commun** . Pour **Valeur** , tapez le nom de sujet que vous utiliserez pour le proxy inverse, puis cliquez sur **Ajouter** . Dans l’exemple fourni dans le tableau de cette rubrique, le nom du sujet est webext.contoso.com et devrait être indiqué dans le champ Valeur du nom du sujet.

9.  Sous l’onglet **Sujet** , sous **Autre nom** , sélectionnez **DNS** dans la liste déroulante **Type** . Pour chaque autre nom du sujet défini dont vous avez besoin sur le certificat, tapez le nom de domaine complet, puis cliquez sur **Ajouter** . Par exemple, le tableau inclut trois autres noms du sujet (meet.contoso.com, dialin.contoso.com et lyncdiscover.contoso.com). Dans le champ **Valeur** , tapez meet.contoso.com, puis cliquez sur **Ajouter** . Répétez cette opération pour chaque autre nom du sujet que vous devez définir.

10. Dans la page **Propriétés du certificat** , cliquez sur l’onglet **Extensions** . Dans cette page, vous devez définir l’objet de la clé de chiffrement dans **Utilisation de la clé** et l’utilisation améliorée de la clé dans **Utilisation de clé étendue (stratégies d’application)** .

11. Cliquez sur la flèche **Utilisation de la clé** pour afficher les **options disponibles** . Sous Options disponibles, cliquez sur **Signature numérique** , puis sur **Ajouter** . Cliquez sur **Chiffrement de la clé** , puis sur **Ajouter** . Si la case à cocher **Rendre ces utilisations de clés critiques** est désactivée, activez-la.

12. Cliquez sur la flèche **Utilisation de clé étendue (stratégies d’application)** pour afficher les **options disponibles** . Sous Options disponibles, cliquez sur **Authentification du serveur** , puis sur **Ajouter** . Cliquez sur **Authentification du client** , puis sur **Ajouter** . Si la case à cocher **Rendre l’utilisation de la clé étendue critique** est activée, désactivez-la. Contrairement à la case à cocher Utilisation de la clé (qui doit être activée), vous devez vérifier que la case à cocher Utilisation améliorée de la clé est désactivée.

13. Dans la page **Propriétés du certificat** , cliquez sur l’onglet **Clé privée** . Cliquez sur la flèche **Options de clé** . Pour **Taille de la clé** , sélectionnez **2048** dans le menu déroulant. Si vous générez la paire de clés et la demande de signature de certificat sur un ordinateur autre que le proxy inverse auquel ce certificat est destiné, sélectionnez **Permettre l’exportation de la clé privée** .
    
    > [!security]  
    > Il est généralement recommandé de sélectionner <strong>Permettre l’exportation de la clé privée</strong> si vous avez plusieurs proxys inverses dans une batterie, car vous devez copier le certificat et la clé privée sur chaque ordinateur de la batterie. Si vous permettez l’exportation de la clé privée, vous devez être prudent avec le certificat et l’ordinateur sur lequel il est généré. Si elle est compromise, la clé privée rendra le certificat inutilisable et exposera potentiellement le ou les ordinateurs aux accès externes et autres failles de sécurité.

14. Sous l’onglet **Clé privée** , cliquez sur la flèche **Type de clé** . Sélectionnez l’option **Exchange** .

15. Cliquez sur **OK** pour enregistrer les **propriétés de certificat** que vous avez définies.

16. Dans la page **Inscription de certificats** , cliquez sur **Suivant** .

17. Dans la page **Où voulez-vous enregistrer la demande hors connexion ?** , vous êtes invité à indiquer un **nom de fichier** et un **format de fichier** pour enregistrer la demande de signature de certificat.

18. Dans le champ **Nom du fichier** , tapez un chemin d’accès et un nom de fichier pour la demande, ou cliquez sur **Parcourir** pour sélectionner un emplacement pour le fichier et tapez le nom de fichier de la demande.

19. Pour **Format de fichier** , cliquez sur **Base 64** ou **Binaire** . Sélectionnez **Base 64** , sauf indication contraire du fournisseur de vos certificats.

20. Recherchez le fichier de demande que vous avez enregistré lors de l’étape précédente. Envoyez-le à votre autorité de certification publique.
    
    > [!IMPORTANT]  
    > Microsoft a dressé la liste des autorités de certification publiques qui respectent les impératifs liés aux communications unifiées. Celle-ci est accessible dans l’article suivant de la Base de connaissances : <a href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</a>.
