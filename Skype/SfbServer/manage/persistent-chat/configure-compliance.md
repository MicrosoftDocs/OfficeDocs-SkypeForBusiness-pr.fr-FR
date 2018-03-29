---
title: Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Résumé : Apprenez à configurer le service persistant conformité du serveur Chat dans Skype pour Business Server 2015.'
ms.openlocfilehash: a77b07b0e05a248c351e73c5b8a5f2cebf97236c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer le service persistant conformité du serveur Chat dans Skype pour Business Server 2015.
  
La conformité de conversation permanente permet aux administrateurs d’archiver les messages de conversation permanente, ainsi que les activités. Le service de mise en conformité qui enregistre et archive les données relatives à chaque conversation permanents Chat Server, y compris lorsqu’un participant :
  
- Joint une salle de conversation permanent
    
- Quitte une salle de conversation
    
- Publie un message
    
- Consulte l’historique d’une conversation
    
- Transfère un fichier
    
- Télécharge un fichier
    
Ces informations sont récupérables au besoin à partir de la base de données SQL de conformité. 
  
## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Configurez le service de conformité à l’aide de Windows PowerShell

Une fois que le service de conformité a été activé à l’aide du générateur de topologie, vous pouvez configurer le service à l’aide de l’applet de commande **Set-CsPersistenChatComplianceConfiguration** :
  
```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

ou
  
```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Vous pouvez définir les paramètres suivants :
  
- AdapterType : permet de définir le type d’adaptateur. Un adaptateur est un produit tiers qui convertit les données dans la base de données de conformité dans un format spécifique. XML est le format par défaut.
    
- OneChatRoomPerOutputFile - ce paramètre permet de spécifier qui séparent les rapports doivent être créés pour chaque salle de conversation.
    
- AddChatRoomDetails : lorsque ce paramètre est activé, des détails supplémentaires sont enregistrés sur chaque salle de conversation dans la base de données. Comme ce paramètre peut considérablement augmenter la taille de la base de données, il est désactivé par défaut.
    
- AddUserDetails : lorsque ce paramètre est activé, des détails supplémentaires sont enregistrés sur chaque salle de conversation dans la base de données. Comme ce paramètre peut considérablement augmenter la taille de la base de données, il est désactivé par défaut.
    
- Identity : ce paramètre permet d’étendre les paramètres de conformité à un ensemble particulier, y compris aux niveaux global, du site et du service. Il est défini sur le niveau global par défaut. 
    
- RunInterval : ce paramètre précise le délai avant que le serveur ne crée un nouveau fichier de sortie de conformité (le délai est défini sur 15 minutes par défaut).
    
## <a name="use-a-customized-compliance-adapter"></a>Utilisez un adaptateur de conformité personnalisé

Vous pouvez écrire un adaptateur personnalisé au lieu d’utiliser le XmlAdapter qui est installé avec le serveur de conversation persistant. Pour ce faire, vous devez fournir un assembly .NET Framework contenant une classe publique qui implémente l’interface **IComplianceAdapter**. Vous devez placer cet assembly dans le dossier d’installation de serveur de conversation permanent de chaque serveur dans le pool de serveur de conversation persistant. Chacun des serveurs de conformité peut fournir des données de conformité à votre adaptateur, mais ils ne délivrent aucun duplicata des données de conformité à plusieurs instances de votre adaptateur.
  
L’interface est définie dans l’assembly Compliance.dll dans l’espace de noms `Microsoft.Rtc.Internal.Chat.Server.Compliance`. Elle définit deux méthodes que votre adaptateur personnalisé doit implémenter.
  
Le serveur de conformité de conversation permanent appellera la méthode suivante lors du premier charge de la carte. Le `AdapterConfig` contient la configuration de la conformité Chat permanent qui est pertinente pour la carte de mise en conformité :
  
```
void SetConfig(AdapterConfig config)
```

Le serveur de conformité de conversation permanent appelle la méthode suivante à intervalles réguliers, tant que les nouvelles données à traduire. Cet intervalle de temps est égal à la `RunInterval` tel que défini dans la configuration de la conformité permanente de Chat :
  
```
void Translate(ConversationCollection conversations)
```

Le `ConversationCollection` contient les informations de conversation qui ont été collectées à partir de la dernière fois que cette méthode a été appelée.
  
## <a name="customize-the-xslt-definition-file"></a>Personnaliser le fichier de définition XSLT

Les données de conformité sont fournies au format XML, que vous pouvez transformer dans le format le mieux adapté à votre organisation, à l’aide du fichier de définition XSLT. Cette rubrique décrit le fichier XML que le service de conformité crée. Elle fournit également des échantillons de fichiers de définition XSLT et de sortie.
  
### <a name="output-format"></a>Format de sortie

La sortie du service de conformité est classée par conversation (l’élément Conversation) puis par message (l’élément Messages), comme illustré dans l’exemple de code suivant :
  
```
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

Un élément Conversation contient quatre éléments (Channel, FirstMessage, StartTimeUTC et EndTimeUTC). L’élément Channel contient l’URI (Uniform Resource Identifier) de la salle de conversation et l’élément FirstMessage décrit le premier message de l’élément Messages. Les éléments StartTimeUTC et EndTimeUTC fournissent les heures de début et de fin pour la conversation, comme illustré dans l’exemple de code suivant :
  
```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Un élément Message contient deux éléments (Sender et DateTimeUTC) et trois attributs (Type, Content et ID). L’élément Sender représente l’utilisateur qui envoie le message, et l’élément DateTimeUTC le moment où se produit un événement, comme illustré dans l’exemple de code suivant :
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

Le tableau suivant décrit les attributs de message Type, Content, et ID.
  
**Attributs de l’élément messages**

|**Attribut**|**Description**|**Facultatif/nécessaires**|
|:-----|:-----|:-----|
|Type  <br/> |Spécifie le type de message. Les types de message sont décrits dans la table Éléments de message Types de message.  <br/> |Obligatoire  <br/> |
|Contenu  <br/> |Contient le contenu du message. Les messages de type Join ou Part n’utilisent pas cet attribut.  <br/> |Facultatif  <br/> |
|ID  <br/> |Spécifie l’ID unique du contenu. Cet attribut est utilisé uniquement avec les messages de type Chat.  <br/> |Facultatif  <br/> |
   
Chaque élément Sender contient cinq attributs : username, ID, email, internal et URI. Ces attributs sont décrits dans la table suivante.
  
**Attributs de l’élément expéditeur**

|**Attribut**|**Description**|**Facultatif/nécessaires**|
|:-----|:-----|:-----|
|Nom d’utilisateur  <br/> |Nom de l’expéditeur.  <br/> |Facultatif  <br/> |
|ID  <br/> |ID unique de. l’expéditeur  <br/> |Obligatoire  <br/> |
|Email  <br/> |Adresse e-mail de l’expéditeur.  <br/> |Facultatif  <br/> |
|Interne  <br/> |Détermine si l’utilisateur est un utilisateur interne ou fédéré. Si la valeur est Vraie, l’utilisateur est interne.  <br/> |Facultatif  <br/> |
|Uri  <br/> |URI SIP de l’utilisateur.  <br/> |Obligatoire  <br/> |
   
Les exemples suivants illustrent les types de messages que l’élément de Messages peut contenir. Elle fournit également des exemples de la manière avec laquelle chaque élément est utilisé.
  
Jointure - un utilisateur joint à une salle de conversation.
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Partie - un utilisateur laisse une salle de conversation.
  
```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Conversation - adresse de messagerie de l’expéditeur.
  
```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat - un utilisateur demande des contenus à partir de l’historique de conversation.
  
```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Téléchargement de fichier - un utilisateur télécharge un fichier.
  
```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Téléchargement de fichier - un utilisateur télécharge un fichier.
  
```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>Sortie de conversation permanent XSD et exemple XSL Transformation par défaut

L’exemple de code suivant contient la sortie par défaut du serveur de conformité :
  
```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>
  
  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

L’exemple de code suivant contient un exemple de transformation XSL :
  
```
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>

```


