# Noteworthy Child 2

This is the second child page of my note taking evaluation. This guid `3fccb56f-2c70-4b91-b008-6ef36368865e` appears on both child pages. This page contains this C# code.

```
using System.Collections.Generic;
using System.Linq;
using Newtonsoft.Json.Linq;

namespace MessageCodeGenerator
{
    public interface ICodeGenerator
    {
        void GenerateCode(IEnumerable<JObject> idl);
    }

    // ReSharper disable once UnusedMember.Global
    public class CodeGenerator : ICodeGenerator
    {
        public CodeGenerator(
            IIdlToModel idlToModel,
            IEnumerable<ILanguageCodeGenerator> languageCodeGenerators)
        {
            IdlToModel = idlToModel;
            LanguageCodeGenerators = languageCodeGenerators;
        }

        private IIdlToModel IdlToModel { get; }

        private IEnumerable<ILanguageCodeGenerator> LanguageCodeGenerators { get; }

        public void GenerateCode(IEnumerable<JObject> idl)
        {
            var model = IdlToModel.Transform(idl);
            LanguageCodeGenerators.ToList().ForEach(generator => generator.GenerateCode(model));
        }
    }
}
```

3fccb56f-2c70-4b91-b008-6ef36368865e appears twice on this page.
